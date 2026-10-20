# Native motion positive training — 2026-10-20, batch 539

本輪訓練已完成，實際產出 **ares-v1.3.110**。固定舊案例回歸及 API 上架尚未完成；目前不能宣稱 X Dash 已穩定改善。

## 資料與變因

沿用 batch 519 的訓練方法，只增加既有 TRAIN 拍攝場景中的 12 張原始正例、23 個 LLM 框。原有 603 組資料與全部 VAL／TEST 保持一致，沒有新增獨立驗收拍攝群組，也沒有使用 batch 529 的合成線性模糊。

| 項目 | 數量 |
|---|---:|
| 全部影像／標籤組 | 615 |
| TRAIN／VAL／TEST 影像 | 514／54／47 |
| 全部／TRAIN LLM 框 | 951／775 |
| TRAIN 負例影像 | 109 |
| 新增至目前 TRAIN 的正例影像／框 | 12／23 |
| 新獨立拍攝群組 | 0 |

標註來源為 LLM，human_confirmed=false、review_status=pending。原始影像先標註並封存，沒有參照候選模型預測框。這些新增資料屬於同一既有 TRAIN camera，不能計入全新驗收資料。

資料準備與漏判分析見 [前一份紀錄](2026-10-20-native-motion-positives-537.md)。

## 實際訓練

只宣告及執行 seed 42；未執行的 seed 43／44 不記為完成或 NULL。

- 完成 30 epochs，batch 4、影像 640、每 epoch 129 個 TRAIN batch。
- 主訓練實際 3,870 次 TRAIN 前向、258 次 optimizer 更新，使用 session-balanced sampling。
- 維持既有 P2-only／背景 floor loss、原有 499 組參數凍結，以及數值與標準 checkpoint 儲存檢查。
- 另有一次拋棄式 GPU 預檢：1 次 TRAIN 前向／1 次更新、0 epochs／0 checkpoint；只改動允許的 8 組 P2 參數，原有 499 組保持一致。
- 上述主訓練數字不包含預檢；建構、訓練內 VAL、checkpoint selector 的所有神經網路呼叫總數沒有另外完整計數。

新入口資料契約、相依變更拒絕、source review admission、loss 與 wiring 檢查均有實際執行紀錄。source review 發現的缺少審查入口問題已經過一次 RED→GREEN 修復；這不代表完整產品測試套件或真實準確率全部通過。

## 權重與驗證選擇

使用原有 54 張 VAL、85 個 LLM 框，在 confidence 0.35、IoU 0.5、640，維持 Precision ≥ 0.98 的選擇條件；不調低門檻。

| 欄位 | 結果 |
|---|---|
| 模型 | ares-v1.3.110 |
| 選中 checkpoint | order 6，即已完成第 7 個 epoch |
| VAL TP／FP／FN | 81／1／4 |
| VAL Precision／Recall | 98.78%／95.29% |
| 通過原有 VAL 精確率條件的 checkpoint | 3／30 |

這些百分比是相對於既有 LLM 參考框的一致率，用於驗證選擇，不能視為全新拍攝場景或人工確認的準確率。主程序原生 exit 0，獨立檢查核對了全部 30 個 checkpoint 雜湊、實際更新紀錄、來源／相依封存與選擇結果；檢查程式沒有另外載入模型。

SHA-256：

- 權重：`bd16751c6b3e0b4a06393ff8ff4ed3537296208978ad4e3534be6b37a122912d`
- 訓練計畫：`4e97cde4fa4a377de5eb64c1c67f55b636fe2fd7d530c2f50a77ae2d3483b33a`
- 訓練 source release：`59a5a64185bf3032fa9f2c4a00726b85217909cf775f79701ffe30dbee38d6a0`
- 完成結果封存：`936aa61fc103c90a4ae7a6e22afe0672f2db9e34bb61f90bad8174603163397f`

## 尚未完成的步驟

固定回歸入口在模型執行前，偵測到兩份本機 API 支援程式與舊相依封存不同，因此停止宣告；該評分嘗試的模型載入／推論都是 0。舊封存及已訓練權重保留，正在核對依賴關係，不能把這次宣告失敗記成評分完成或重新訓練成功。

本輪尚未新增 API 選項。最後一份已完成的 API 驗收為 84 choices／166 registry files；之後必須以實際新權重完成回歸、獨立重算、一次發布、指定模型 synthetic job、annotation HTTP 200 及新舊選單／檔案／default／shared state 檢查，才能記錄上架完成。

穩定改善目標仍未達成：至少 3 個未使用拍攝場次、300 個預先封存 LLM 框、固定 confidence 0.35／IoU 0.5，Precision 與 Recall 都 ≥ 90%。本輪單一 seed、同一 TRAIN camera 的新增資料與舊回歸，都不能替代這個最終門檻。

本儲存庫只保存整理後紀錄，沒有上傳影片、影像、標註原檔、權重、私有程式碼或憑證。
