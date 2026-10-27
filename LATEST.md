# 訓練與評估索引

目前更新至第 183 輪；仍未取得合格晉升版本。183完成2,610updates，選25epoch已受learner訓練，pair VAL precision／recall100%、BCE0.009072，但Byte TP635／certain520、原命中流失27，差於182的653／526／23。完整40/136仍退步，拒絕晉升並清理權重。同183tensor用舊政策的932更新／68比較完全相同，不能把退步歸因新政策。180–189目前4次實際訓練10,440updates、零合格與零API晉升。

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

第177輪後：[原生配對／ReID原因診斷](evaluations/round-177-native-cause-diagnosis.md)完成932次盲回放更新，逐欄位重現基準；71個有強sensor的Kalman漏點中44個被所有可用軌跡的Mahalanobis gate拒絕，137個observed-uncertain點另有原生appearance/ReID證據失敗。零optimizer，沒有放寬gate或重判177。

第178輪：[TRAIN預測位置壓力測試完整報告](runs/run-178.md)完成30epochs／2,610 optimizer updates；165,450 base-pair訪次中74,971次為明確標示的合成輸入，VAL215保持原樣。pair TP／FP／FN／TN＝152／0／4／59，recall97.44%僅代表已知配對。完整追蹤32/136項退步，Kalman TP708不變、Byte545→547，零來源群同時通過兩profile，拒絕晉升、權重已清理。[學習曲線](runs/run-178-learning-curve.json)。170–179視窗目前9次實際訓練／11,567 updates／零合格與零API晉升。

第178輪後：[整組有證據替換preflight](evaluations/round-178-certified-replacement-preflight.md)完成16項行為／float32門檻控制，FIT1,700與完整3,728次停用／中性更新逐欄位一致；這些為機制與相容控制，零optimizer，非品質改善。

第179輪：[相同分類器重現＋採用規則完整報告](runs/run-179.md)完成30epochs／2,610實際更新，每epoch loss／VAL與178精確一致，非獨立新表示。完整32/136項仍退步，但studio-fast-rail的Kalman certain18→24、橘色最長certain缺口6→2；全體Kalman certain531→537，尚無來源群通過兩profile門檻，拒絕晉升。失敗權重已清理，21054筆scalar scores保留；71個強sensor Kalman漏點中62個被評分卻全低於.95、9個無可用pair。[學習曲線](runs/run-179-learning-curve.json)。

[第170–179輪十次訓練總檢討](evaluations/round-170-179-window-review.md)：14,177實際optimizer updates，零合格與零API晉升，不以失敗變體補足五個名額。九個既有API權重完整，穩定高速／模糊軌跡改善目標持續。


第179輪後：[素材來源稽核與外觀特徵前置驗證](evaluations/round-179-source-family-and-appearance-preflight.md)：72影格／144中心點來自既有攝影來源群，零新增獨立來源，均未准入TRAIN；39維外觀純函式通過因果與缺失控制，但尚未整合或訓練。零新增optimizer updates，最新實際訓練仍為179，未產生第180輪或新準確率。


第180輪：[實際觀測外觀39維完整報告](runs/run-180.md)完成30epochs／2,610實際更新；215個已知VAL配對TP156／FP0／FN0／TN59，precision／recall100%。完整Kalman TP708→721、certain531→594；Byte TP545→601、certain440→531，但40/136比較仍退步、零來源群同時通過兩profile。拒絕晉升，候選已清理、九個API權重不變。[學習曲線](runs/run-180-learning-curve.json) · [136比較及精準度摘要](runs/run-180-metrics.json)。新視窗180–189目前1次訓練／零合格，穩定高速／模糊軌跡目標持續。


第180輪後：[共同命中分解與learner-state前置驗證](evaluations/round-180-composition-and-learner-state-preflight.md)：Kalman原708TP全保留、共同量測不變；Byte原545TP中流失46點、另新增102點，不能以淨增56掩蓋流失。TRAIN-only控制核對5515原配對精確相同，非學習控制產生792筆新Byte狀態配對，但控制資料未准入optimizer。零新增訓練，最新實際輪次仍為180；181須改用真正當前模型快照驗證。全套本機產品檢查通過，原拒絕及API不變。


第181輪：[真正當前模型狀態TRAIN續訓完整報告](runs/run-181.md)完成30epochs／2,610updates，epoch10／20快照產生814／802筆新狀態配對、實際混入55,140訪次。最佳epoch25已受learner資料訓練，215 VAL precision／recall100%、BCE0.001867。Kalman TP722／certain594；Byte TP609／certain496，原命中流失32（180輪46），但完整40/136仍退步且零來源群通過兩profile。拒絕晉升，權重清理完畢、九個API權重不變。[曲線](runs/run-181-learning-curve.json) · [136比較與精準度](runs/run-181-metrics.json) · [learner資料稽核](runs/run-181-learner-admissions.json)。180–189視窗目前2次實際訓練、5,220updates、零合格。


第181輪後：[封存分數精確重播與綁定診斷](evaluations/round-181-exact-policy-binding-diagnosis.md)：14案例／932更新／3689封存分數精確重現，零新NN或optimizer。32個原Byte命中流失中31個core感測已送出但ID與guard綁定不符，另1個原生guard拒收；certain相較180輪54失去／19新增，淨減35。85條改變邊含44未綁定、41已綁定，不能假設只禁止未綁定即可修好。下一提案資格機制尚未實作，第182輪未啟動；原拒絕與API不變。


第182輪：[有效guard綁定與下游資格完整報告](runs/run-182.md)完成30epochs／2,610updates，實際55,140 learner訪次；最佳epoch10卻在learner混入前、tensor精確同180，故驗收差異歸於policy。Byte TP653／certain526，原命中流失23（180:46、181:32），但40/136仍退步、零來源群通過兩profile，拒絕晉升；本機九個API權重不變。保存14220真NN分數與獨立棄權紀錄。[曲線](runs/run-182-learning-curve.json) · [136比較](runs/run-182-metrics.json) · [learner／TRAIN-only診斷](runs/run-182-learner-admissions.json)。180–189共3次訓練／7,830updates／零合格，下一正動作資格／負證據分離假說尚未實作。


第183輪：[正動作資格／負證據分離完整報告](runs/run-183.md)完成30epochs／2,610updates，實際55,140learner訪次，選25epoch（新tensor）。Byte TP635、certain520、原命中流失27，仍40/136退步、零來源群通過兩profile。固定同tensor舊政策診斷與本輪所有輸出／68指標完全相同。既有41個VAL影格的時序study可分出known-detector命中155→160，但certain88不變且不能測完整物理定位／場外FP；下一步先凍結時序DEV而非再只看pair BCE。[曲線](runs/run-183-learning-curve.json) · [136比較](runs/run-183-metrics.json) · [learner／控制／VAL與fold稽核](runs/run-183-diagnostics.json)。候選已清理，本機9個API權重不變；180–189目前4次／10,440updates／零合格。
