# TRAIN座標與分類分數交換前置診斷

同146TRAIN／259既有bodyGT、640square、8400相同anchor grid；三組原生raw經原conf0.35／NMSIoU0.5／一對一GTIoU0.5重播，精確重現teacher255TP4FN15未配對、selected189258TP1FN14未配對、final189259TP0FN0未配對。

| 逐anchor座標 | 分類分數 | TP／FN／未配對 |
| --- | --- | ---: |
| Ares33 | selected189 | 258／1／14 |
| Ares33 | final189 | 259／0／0 |
| selected189 | Ares33 | 255／4／15 |
| final189 | Ares33 | 255／4／15 |

全部8empty的FP皆0。七組共1022個NMS影格處理，零NN呼叫／optimizer／checkpoint檔。這將現有TRAIN的命中改善歸於分類分數變化，支持下一個固定bbox的訓練實驗；不是獨立驗證、可部署模型、泛化或未來class-only optimizer結果的證據。bbox固定也可能因分數／NMS而改變最後中心。

第189輪原選擇、正式拒絕與API不變；沒有新的標註、heldout推論或閾值變更。第190輪仍須通過原高速／模糊軌跡及既有案例門檻。所有標註是同助理複核，非獨立人工真值。
