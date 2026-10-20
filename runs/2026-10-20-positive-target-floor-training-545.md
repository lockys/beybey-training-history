# 545：正樣本分類目標下限 0.5，完整訓練後未通過選取

日期：2026-10-20。這是一次正常完成、結果未達既定條件的實驗。沒有產生可發布的 ares-v1.3.111 權重，也沒有宣稱精準度或穩定性改善。

## 實際訓練

- 只有 seed 42，從原始初始化權重開始，沒有接續 v1.3.110 或重啟失敗訓練。
- 主訓練完成 30 epochs、3,870 次 TRAIN forward、258 次實際 optimizer updates；原生程序正常結束。
- GPU 單步預檢另有 1 次 TRAIN forward、1 次 update，之後丟棄；不算入主訓練，也不產生候選 checkpoint。
- 唯一學習變更：分類 BCE 中原 target 大於 0 的項目，以新副本設定最低 target 0.5。零目標的既有 gamma 2／floor 0.5 權重不變；TAL、bbox／DFL 的原 target 和原 normalizer 不變。
- 原始 499 entries 保留、P2-only 訓練、初始化、LR 與 sampler 條件延續前輪。實際累計 71,456 個 soft-positive 分類項目受到下限影響；這是訓練項目數，並非新增物件或標註數。

資料仍為 615 pairs：TRAIN 514、VAL 54、TEST 47；合計 951 個 LLM 框，其中 TRAIN 775 框、TRAIN 負樣本影像 109 張。本輪新增影像 0、LLM 框 0、獨立拍攝場次 0。歷史 537 輪補入的 12 張影像／23 框不重複算成這輪新增。標註來源為 LLM，human_confirmed=false。

## 固定 VAL 的實際結果

VAL 仍是 54 frames／85 boxes，confidence 0.35、one-to-one match IoU 0.5、NMS IoU 0.5、image size 640。最低 Precision 98% 的選取條件沒有調低。

| 項目 | 結果 |
| --- | --- |
| 完成並檢查的 checkpoints | 30 |
| 通過既定 VAL 條件 | 0 |
| 每個 checkpoint 的 FP 最低值 | 2 |
| 最高觀察到的 VAL Precision | 97.56% |
| 該觀察值的 TP／FP／FN | 80／2／5 |
| 該觀察值的 Recall | 94.12% |
| 實際 selected | NULL |

最高觀察值來自 order 5／第 6 個完成 epoch，僅為既有 VAL 結果的事後摘要，並非選出的權重。所有 checkpoints 都至少有 2 個 FP；因此沒有一份達到原定 98% Precision 條件。這次設定未通過，不代表其他目標下限設定或其他資料一定無效。

沒有選取權重，所以沒有對高速／舊 324 框參照集執行新模型推論。這些未執行的測試不能記作零誤報、零漏判或已通過；也不能沿用 v1.3.110 的分數作為 v1.3.111 的分數。

## 驗證與後續流程

獨立 root checker 以零模型載入核對 30 份 checkpoint 雜湊、18 個 prospective source 項目、575 個宣告的 executable sources、3,870 筆 batch 記錄、258 筆 step 記錄及 30 個 sampler epochs。原始 entries 保存與 serialization 的實際檢查來自 worker 斷言和 phase evidence；root checker 不會重新載入模型。constructor／VAL／selector 的全部神經呼叫次數沒有獨立計數。

546 已正常完成這個實際完成的 NULL 來源記錄，獨立 root checker 也已通過：實測模型載入 0、predict 0、神經 root forward 0、新增訓練 0。沒有實際選取權重，因此未執行候選的影片評分，fast／large 結果皆為 NULL。

評估來源審查曾發現：宣告中的訓練輸入可能雜湊正確，卻不在上游封存清單內。已用 public origins 行為測試先觀察失敗，再修正為逐一檢查封存成員資格及宣告雜湊；缺少依賴和依賴雜湊不符都會拒絕。完整 focused suite 通過；沒有第二次審查或神經重試。固定影格、框、門檻、評分器與六個共用 helper 保持原樣。

547 僅保留預先準備的發布草稿，未開始 API prepare／register／合成影片上傳。這輪沒有新權重可推送。上次已驗證的 API 版本仍是 [539／542／543 記錄中的 v1.3.110](2026-10-20-native-positive-training-539.md)，當時為 85 個選項／168 個 registry files；本輪未重新驗證 API 選單，也未對它進行寫入或預設模型提升。

另做了兩輪、有界的公開網路搜尋，只記錄影片候選的公開資訊；沒有新的影片下載、影格標註或獨立驗收資料加入本輪。先前指定的定性示例仍僅供定性參考。

## 可追溯性與判定

- 545 training plan SHA-256：be121d6edee63ef74c525e846dafd067324d76fe81b6b89a81b384b51b19ce69
- 545 source release SHA-256：47bef1aaf6e2d18a51607e69b38f04c6179f477653f5c382d4364e590b1f9863
- 545 closed manifest SHA-256：5370addf8842c09c07fdab7ec8d31f05a394dea09fff858ced44731fadcbe727
- 546 source release SHA-256：c9d6a3d5430e5073be4761bd4019b2cd9a8b5f7996260d20963e3ffcc0eab068
- 546 input declaration SHA-256：67f78372d77698aa946f69bcdf131ab97cc7e4ef47ec27601b912d27a3074563

本紀錄只公開整理後的實驗結果；不含媒體、權重、私有程式碼、憑證或本機路徑。所有階段和原生證據保留。Focused research checks 不代表 backend／UI／Android 全套測試已重新通過。

判定：在不降低選取門檻的前提下，拒絕本輪 target floor 0.5 設定。stable_improvement_proven=false。最終驗收仍需至少 3 個未使用的獨立拍攝場次、至少 300 個預先凍結的 LLM 框，在 confidence 0.35／IoU 0.5 下 Precision 和 Recall 同時至少 90%；本輪沒有完成這項驗收。

前置診斷：[544 診斷及當時的 CPU-only 545 草案](2026-10-20-positive-target-diagnostic-544.md)。本紀錄補上其後實際完成的訓練結果，沒有將先前的 CPU-only 證據改寫成已完成訓練。
