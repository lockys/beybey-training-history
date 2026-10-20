# BEYBEY 訓練紀錄：2026-10-20

此紀錄整理 X Dash 高速移動漏判的研究進度。所有數字依實際執行紀錄；LLM 標註與既有回歸集的結果屬探索性證據，尚未證明真實影片有穩定改善。

## 固定設定與資料

- 資料共 603 組影像／標註：TRAIN 502、VAL 54、TEST 47；TRAIN 含 109 張負例。
- 既有標註 928 個框，另有 28 份 hard-negative replay 複本。複本不是新的獨立拍攝場次。
- 640 輸入、batch 4、30 epochs／seed；每組 3,780 次 TRAIN forward、252 次 optimizer update。
- 名目 learning rate 為 5e-5，實際 optimizer step 套用 100 倍乘數，warmup 1 epoch；AMP 關閉、mosaic 0、workers 0，使用場次平衡抽樣。
- background loss 為零目標位置的 `(1 + sigmoid(logit)^2) × BCE`；正例維持既有 TAL／BCE。
- 只訓練 P2；原模型的 499 個 state entries 保持不變。每組從原始 initializer 開始。
- VAL 選擇：precision 至少 0.98，再按 recall、較少 FP、較早 epoch 排序；54 張影像、85 個框。VAL 結果不是獨立驗收結果。
- 固定評分使用 confidence 0.35、IoU 0.5；不藉由修改門檻宣稱改善。

## 已完成的比較

TP／FP／FN 為既有 LLM 參考集的計數。fast 集與 324-box 集是分開的固定回歸範圍，不能視為新增資料。

| 批次／版本 | 實際動作 | fast TP/FP/FN | 324-box TP/FP/FN | 結果 |
| --- | --- | --- | --- | --- |
| 固定基準 | 既有固定參考 | 45/2/7 | 320/26/4 | 比較基準 |
| 519→520／.101 | background floor loss，30 epochs | 47/5/5 | 323/37/1 | 固定嚴格回歸未通過 |
| 519→520／.102 | 同設定、不同 seed，30 epochs | 45/2/7 | 322/61/2 | 固定嚴格回歸未通過 |
| 519→520／.103 | 同設定、不同 seed，30 epochs | 45/2/7 | 321/35/3 | 固定嚴格回歸未通過 |
| 525→526／.105 | 502 張 TRAIN 做一次 P2 BN 統計校準；0 新 epochs／0 更新 | 45/2/7 | 322/62/2 | 固定嚴格回歸未通過 |
| 525→526／.106 | 同校準、不同 seed；0 新 epochs／0 更新 | 45/5/7 | 321/37/3 | 固定嚴格回歸未通過 |

525 的 seed42 在寫出最終 checkpoint 時失敗；`.104` 不存在可用的最終輸出，也未上架。519 三組共實際 90 epochs、11,340 次 TRAIN forward、756 次更新；525 校準不應累計為訓練 epochs。

## 529：固定 motion blur 訓練

528 的合成機制測試曾抓到固定 seed 只能取到兩個方向；修正後確認每個 epoch 四個方向都會使用，再進入實際訓練。這只是增強機制測試，並非準確率證明。

在上述 floor loss 設定加入 TRAIN 專用的線性 motion blur：kernel 9、reflect padding、四個方向、每批約半數影像。VAL／TEST 不套用此增強。每組實際應模糊 7,530 張訓練輸入；此數字包含跨 epoch 重複，不是新增影像。

| seed | 訓練狀態 | VAL 選擇 | 後續 |
| --- | --- | --- | --- |
| 42 | 已完成 30 epochs／3,780 TRAIN forward／252 更新 | 無 checkpoint 通過固定 VAL precision 門檻 | 不產生 `.107` 可選權重 |
| 43 | 已完成 30 epochs／3,780 TRAIN forward／252 更新 | `.108`：選中第 11 epoch；VAL 82/1/3 | 531 固定回歸未通過；fast 45/2/7，324-box 323/55/1 |
| 44 | 已完成 30 epochs／3,780 TRAIN forward／252 更新 | `.109`：選中第 10 epoch；VAL 82/1/3 | 531 固定回歸未通過；fast 45/2/7，324-box 323/44/1 |

`.108` SHA-256：`2121ba7f1e9add07c96aaea9fe3a145dba67525f3dcbe6d7454d26ad3a329115`。

`.109` SHA-256：`a63e05b8f8699cdba5ed7ce5fb14b79196a03a5c9707eaff417b2b4685410b5b`。

529 三組共實際完成 90 epochs、11,340 次 TRAIN forward、756 次更新及 22,590 張重複的模糊訓練輸入。

531 每個實際權重均完成 8 次 model load、244 次 predict、251 次觀察到的 root forward；兩組合計 16／488／502，評分新增 epochs／optimizer updates 均為 0。空結果那一組沒有額外模型載入或推論。兩個新版的高速參考集都與基準相同，大型集雖少 3 個 FN，卻有更多 FP，因此未達固定嚴格回歸要求。

訓練進度與原生程序結果已核對；TRAIN forward 計數不包含另外未獨立統計的模型建構、VAL 及 checkpoint 選擇推論。

## 公開影片蒐集

此輪一個公開 YouTube 候選影片可正常觀看，但既定下載格式不可用；該次蒐集已結束，未切換 client、登入資訊或格式重試。這次新增影片、影格及標註框均為 0。無法把 motion blur 增強算成收集到新的 X Dash 實拍樣本。

## API 狀態

527 已驗證 `.105`／`.106` 為本機 API 選項。532 現已將 `.108`／`.109` 加入同一 API 選單，共 **84 個選項、166 份 registry 檔案**；原有 82 個選項及 162 份檔案均保留，預設模型與共用訓練狀態未改變。

兩個新版本共用一段只有 2 張 320×320 黑畫面的合成影片，各提交一次明確 model ID 的工作。兩個工作均完成，實際權重 SHA 與上述版本相符；服務回傳的有效設定符合 `image_size=640`、`confidence=0.35`、`iou_threshold=0.5`，標註下載皆為 HTTP 200。所有工作完成後，又重新核對選單、registry、health/default 及共用狀態。

上架前的來源檢查補強了舊 registry 基準的固定雜湊、所有有效工作設定及最後副作用後的保留性閘門；純資料回歸測試拒絕 11 個不符合案例。

**合成影片只證明版本可選與推論流程可運作，不證明準確率。** 兩個新版維持實驗版；未驗證公開 gateway 或雲端同步。

## 驗證限制與下一步

- 尚未達成全新的至少 3 個獨立拍攝場次、300 個凍結參考框、precision／recall 均至少 90% 的獨立驗收。
- 既有參考已被使用多次；`human_confirmed=false`、`stable_improvement_proven=false`，所有候選維持實驗版。
- 研究用的 motion blur、原生執行來源及 metadata admission 測試已執行。UI unit 42 tests、e2e 39 tests 通過；Android Gradle 成功但 unit task 為 cached/up-to-date。後端／annotator 廣泛檢查有相依／環境錯誤，後續兩次檢查停滯後已中止，無完整通過結論。
- 下一輪繼續尋找可合法取得的 X Dash 實拍影片，建立新的獨立凍結參考；不能把這次 motion blur 增強或既有回歸集重測算成新增驗收資料。

本 repo 僅發布整理後的研究設定、計數、狀態及雜湊；不含影片、影像、權重、原始日誌、私人程式碼、機器路徑或憑證。
