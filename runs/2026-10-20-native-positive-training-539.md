# Native motion positive training — 2026-10-20, batch 539

本輪訓練、固定舊案例回歸及本機 API 上架均已完成，實際產出 **ares-v1.3.110** 並可選用。高速案例仍有 7 個漏判，**尚未證明 X Dash 已穩定改善**；保留原預設模型。

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

## 固定回歸結果（batch 542）

首次 batch 540 在模型執行前因兩份 API 支援程式的舊相依封存不同而停止，模型載入／推論均為 0；沒有重跑或改寫舊封存。新 batch 542 事先核對並宣告這兩份支援程式的實際版本，加入模型執行前的禁止載入檢查，保留相同參考影像、框、評分器及 confidence 0.35／IoU 0.5／640。

一次實際評分的原生程序 exit 0：8 次模型載入、244 次 predict、251 次觀察到的 root forward（175 次 CPU predict、69 次 GPU predict）。本階段沒有新增訓練或 optimizer 更新。另由沒有載入模型的檢查程式核對相依封存、原生完成紀錄與全部 241 張有框影像、3 張空白／場地影像的儲存預測。

| 已消耗的參考組 | TP／FP／FN | Precision／Recall |
|---|---:|---:|
| 高速相關組 | 45／2／7 | 95.74%／86.54% |
| 324 框舊參考組 | 321／49／3 | 86.76%／99.07% |

舊參考組另有 3 個空白影像誤判。高速漏判數與前兩個實驗選項相同；本輪未通過嚴格改善條件。上述為 LLM 參考框一致率，human_confirmed=false；舊資料回歸不能作為全新拍攝場次的驗收。

- 評分 source release SHA-256：`8c02d954449189c1e223130e113aec97926371b2e1304c908454463181d3bbf9`
- 評分輸入宣告 SHA-256：`0c8495b802ea568c8a03d596abf00a6685b15fff37537e9202834d711ec90345`
- 評分完成封存 SHA-256：`d0345f00f377f3a5bfadcd00b1a504321aabf6bb90605a023cb72f1a12167e32`

## 本機 API 上架（batch 543）

已把實際 v1.3.110 權重加入既有本機 API registry，作為實驗版選項。上架與最後驗收均為實際原生 exit 0：

- 選單從 84 增至 **85 個模型選項**，registry 從 166 增至 **168 個檔案**；舊選項及檔案雜湊全部保留。
- 原預設權重與 shared state 雜湊不變，沒有把本輪候選設為預設。
- 使用兩格 320×320 的合成黑色影片，明確指定 `ares-v1.3.110`，實際工作完成、權重 SHA-256 符合，annotations 下載 **HTTP 200**。
- 工作有效參數為影像 640、confidence 0.35、IoU 0.5；只驗證選用／載入／API 整合，不能當作偵測品質證據。
- 沒有上傳私人影片，沒有驗證公共 gateway，也沒有同步 Railway。

發布計畫 SHA-256：`ffea3c64acbf5089d4137f20e7a235b192e7e0f5f432902bde75891b079e1989`  
發布收據 SHA-256：`42694e776d9cb9a75e121f7f3f909f50ab6f43a1afbe8efa75da497e7d2fb675`  
最終驗收 SHA-256：`4859eaf8b8f3f5b6b13b4c245832b41672e24bcec113afadc1e35b364c67b902`

## 仍待達成的驗收

穩定改善目標仍未達成：至少 3 個未使用拍攝場次、300 個預先封存 LLM 框、固定 confidence 0.35／IoU 0.5，Precision 與 Recall 都 ≥ 90%。本輪單一 seed、同一 TRAIN camera 的新增資料與舊回歸，都不能替代這個最終門檻。

本儲存庫只保存整理後紀錄，沒有上傳影片、影像、標註原檔、權重、私有程式碼或憑證。

