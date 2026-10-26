# 評估語意與限制

- Detection precision = TP/(TP+FP)，recall = TP/(TP+FN)，F1 = 2TP/(2TP+FP+FN)。零分母留 null，不捏造分數。每份 JSON 保留分子、分母及來源 cohort。
- LLM／程式產生的參考標註不代表獨立人工真值；未取得人工真值準確率標示 null。
- 追蹤另外評估觀測覆蓋、確定觀測、FN、FP_proxy、斷軌、碎片、ID 誤配與中心誤差。FP_proxy 不可用來推導 precision。沒有身分標註的片段不能證明身分辨識準確。
- 內部 pair score、單步 forecast NLL／誤差、實際追蹤回放、完整產品端到端驗收分別記錄。內部通過不代表 API 合格。
- 重建固定集有 14 cases、466 case-frames、461 unique images、796 target observations；原六案例缺失仍標 missing/unverified。兩次助理標註參考不是獨立人工驗收。
- 163–168 的完整追蹤研究回放沿用固定 detector caches、建立新的 tracker 狀態；每模式 136 比較，68 detector 比較沿用封存基準。不是重新執行 YOLO，也不是正式產品驗收。
- 原逐案例非退步要求及至少兩個來源群的改善門檻保留；每十次實際訓練最多挑五個合格候選，不為填滿數量保留或發布不合格權重。
- 每輪訓練、評估與保留決策完成後更新同一份報告，pending 階段不可寫為成功。既有報告保留；公開同步只含數值摘要、判定與雜湊。
