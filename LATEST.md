# 訓練與評估索引

目前更新至第 177 輪；仍未取得合格晉升版本。169 內部預測通過，但完整追蹤研究回放 36/136 比較退步，拒絕晉升並已清除不合格 checkpoint。160–169 共十次實際訓練、6,720 optimizer updates、零晉升。143 原程序失敗，恢復評估另記。142–169 沒有已通過全套驗收的 API 晉升。

[第 142 輪](runs/run-142.md)（原程序失敗後另行稽核及比較）。

| 輪次 | optimizer updates | 狀態 | API 晉升 |
| --- | ---: | --- | --- |
| [143](runs/run-143.md) | 282 | worker_failed_then_recovered_evaluation_rejected | 否 |
| [144](runs/run-144.md) | 282 | not_qualified | 否 |
| [145](runs/run-145.md) | 282 | not_qualified | 否 |
| [146](runs/run-146.md) | 282 | not_qualified | 否 |
| [147](runs/run-147.md) | 282 | not_qualified | 否 |
| [148](runs/run-148.md) | 310 | not_qualified | 否 |
| [149](runs/run-149.md) | 310 | not_qualified | 否 |
| [150](runs/run-150.md) | 310 | not_qualified | 否 |
| [151](runs/run-151.md) | 310 | not_qualified | 否 |
| [152](runs/run-152.md) | 330 | not_qualified | 否 |
| [153](runs/run-153.md) | 330 | not_qualified | 否 |
| [154](runs/run-154.md) | 324 | not_qualified | 否 |
| [155](runs/run-155.md) | 344 | not_qualified | 否 |
| [156](runs/run-156.md) | 344 | not_qualified | 否 |
| [157](runs/run-157.md) | 344 | not_qualified | 否 |
| [158](runs/run-158.md) | 347 | not_qualified | 否 |
| [159](runs/run-159.md) | 347 | not_qualified | 否 |
| [160](runs/run-160.md) | 150 | not_qualified | 否 |
| [161](runs/run-161.md) | 300 | not_qualified | 否 |
| [162](runs/run-162.md) | 510 | not_qualified | 否 |
| [163](runs/run-163.md) | 510 | not_qualified | 否 |
| [164](runs/run-164.md) | 960 | not_qualified | 否 |
| [165](runs/run-165.md) | 930 | not_qualified | 否 |
| [166](runs/run-166.md) | 300 | not_qualified | 否 |
| [167](runs/run-167.md) | 1020 | not_qualified | 否 |
| [168](runs/run-168.md) | 1020 | not_qualified | 否 |
| [169](runs/run-169.md) | 1020 | not_qualified | 否 |

原有 141 以前紀錄留在各歷史目錄。公開報告不包含權重、原始影格、標註或 API 設定。


第 170 輪已完成：[完整報告與評估](runs/run-170.md)（1,020 updates；完整追蹤32/136項退步，零來源群通過改善門檻，拒絕晉升；不合格權重已清理）。[原生配對診斷](evaluations/round-169-native-association-diagnosis.md)。


第 171 輪：[原生 TRAIN 配對完整報告](runs/run-171.md)已完成，1,020 updates、原生配對1,710 visits／2,370 negative-pair visits；完整追蹤32/136項退步，零來源群通過改善門檻，拒絕晉升，不合格權重已清理。


第172輪：[全原生狀態配對完整報告](runs/run-172.md)已完成，1,020 updates；完整追蹤48/136項退步、1個來源群通過改善門檻（至少需2），拒絕晉升，權重已清理。另封存1,150個FIT實際狀態供後續診斷，不是新訓練或真值。


第173輪：[zero／policy-state混合FIT完整報告](runs/run-173.md)已完成，1,020 updates；完整追蹤48/136項退步、1個來源群通過改善門檻（至少需2），拒絕晉升，權重已清理。另附候選可用性與配對診斷；170–179視窗目前4次訓練、4,080 updates、零合格及零API晉升。

第173輪後：[因果配對提案對照](evaluations/round-173-assignment-proposal-controls.md)完成24項行為檢查、FIT 1,360與完整固定集3,728次tracker updates的中性／隔離驗證；零修正逐欄位一致。零新訓練、零新權重與零API晉升，尚未證明品質改善。

第174輪：[因果mean-only配對提案完整報告](runs/run-174.md)已完成1,020 updates；primary Kalman／Byte TP為739／578（基準708／545），但完整追蹤48/136項退步、僅1個來源群通過改善門檻（至少需2），拒絕晉升，權重已清理。170–179視窗目前5次實際訓練／5,100 updates／零合格與零API晉升。

第174輪後：[共同命中分解與偵測定位preflight](evaluations/round-174-composition-and-detector-localization-preflight.md)完成；Kalman原708TP量測不變，Byte實際流失14TP，原拒絕維持。新定位分支機制與TRAIN-only backward通過，零optimizer updates。

第175輪：[標準YOLO bbox末層完整報告](runs/run-175.md)已完成30epochs／5,220batches／實測347 optimizer updates；54張VAL precision98.80%／recall96.47%維持基準，early gate通過，但完整1,864次新推論的204比較有144項退步、零來源群通過改善門檻，拒絕晉升，權重已清理。170–179視窗目前6次實際訓練／5,447 updates／零合格與零API晉升。

第176輪：[current-pair association 完整報告](runs/run-176.md)已完成30epochs／900 optimizer updates；215個來源隔離已知pair的TP／FP／FN／TN＝153／0／3／59（非整段軌跡準確率）。完整追蹤32/136項退步；Byte單profile三來源改善，但Kalman沒有改善，零來源群通過兩profile要求，拒絕晉升、權重已清理。170–179視窗目前7次實際訓練／6,347 updates／零合格與零API晉升。

第177輪：[TRAIN 跳幀配對完整報告](runs/run-177.md)完成30epochs／2,610 optimizer updates；新增3,656 TRAIN配對，VAL215保持不變。pair precision100%／recall96.79%僅代表已知配對，低於176輪recall98.08%。完整追蹤28/136項退步；Kalman仍無改善，Byte primary TP545→541，零來源群通過兩profile改善，拒絕晉升，權重已清理。[學習曲線](runs/run-177-learning-curve.json)、[TRAIN採用與跳幀診斷](evaluations/round-176-TRAIN-adoption-and-cadence.json)。170–179視窗目前8次實際訓練／8,957 updates／零合格與零API晉升。
