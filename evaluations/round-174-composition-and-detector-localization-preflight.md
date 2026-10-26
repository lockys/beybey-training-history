# 第174輪後：共同命中分解與偵測定位開訓前檢查

原174拒絕判定不變；本診斷零optimizer updates，不降低任何驗收門檻。

只取primary24px／repeat0／scenario0，每案例每profile一次，沿用凍結scorer matching與reference；逐案例TP／certain／matched mean重新核對一致。結果不是獨立人工準確率。

| 分解 | Kalman | Byte |
| --- | ---: | ---: |
| Baseline TP | 708 | 545 |
| 兩者共同TP | 708 | 531 |
| 共同TP成對平均誤差變化 | 0.000px | 0.000px |
| 共同TP量測位置完全相同 | 708／708 | 531／531 |
| 新增TP | 31 | 47 |
| 流失的baseline TP | 0 | 14 |
| 新增TP平均殘差 | 6.735px | 3.627px |
| 流失TP平均殘差 | — | 2.651px |

Kalman舊命中未受損，matched mean增加來自新增難例的組成；Byte則有14個真實舊命中流失（cohort-event11、cohort-studio3），不能把全部退步說成統計組成。共同TP相同也不代表整個identity／gap／fragmentation不變。完整48/136退步及來源群1/2不足的拒絕保留。

## 回到標準YOLO定位的機制檢查

為改善原生量測中心，準備從Ares33重新做bbox-only續訓，不再只調motion forecaster。標準原架構三尺度bbox distribution最後Conv2d的weight/bias，共6 tensors／12,480參數；493個其他state凍結，包含分類分支、backbone、neck、bbox feature層與BN統計。沒有新增自訂推論層。

- 合成3次forward驗證：bbox perturbation能改變decoded boxes，raw與decoded class scores逐值一致；六個gradient tensors有限且非零，backward未修改state。
- memory-only half checkpoint roundtrip，493個凍結state精確一致；建立optimizer但未step。
- 兩個in-memory破壞控制均被拒絕：解凍分類器使class autograd隔離失敗；解凍整個bbox分支使gradient ownership失敗。原檔未改寫。
- 既有資料695TRAIN／54VAL／47TEST、1,592 image/label引用SHA核對一致；TRAIN有1,086框／123empty，VAL85框。與目前固定驗收影格無直接image SHA重疊、目前manifest不含驗收source IDs；歷史pretraining來源排除仍未證實。
- 按manifest預選4張TRAIN（old／state／white／gray）、共10GT，1次GPU vendor loss backward；六個gradient tensors有限，其中四個非零，所有state未改，沒有optimizer instance或step。未用VAL/TEST/驗收影格選probe。

既有110張空間合成模糊明記；native補充不是新獨立驗收群，標註不是獨立人工真值。初版preflight有兩個介面錯誤（舊packet key假設、vendor loss items現在是dict），修正後完整檢查通過；沒有把失敗算訓練或恢復checkpoint。NMS／selected anchors可能隨框改變，分類分數固定不能保證FP或軌跡不變。

必要產品檢查通過：backend398／8 skipped、annotator/beytrack163與coverage94.29%（門檻92%）、UI42、e2e39、UI build與Android單元測試成功。仍無新合格權重或API晉升。正式訓練另記[第175輪](../runs/run-175.md)，其完成、準確度與完整軌跡驗收仍待確認。
