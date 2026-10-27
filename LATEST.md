# 訓練與評估索引


第191輪後的原始素材與參考點品質診斷已補充：八張原始影格的主體數量與教師框數相符，尚無新定位真值或TRAIN准入；23張開發參考點的完整第二次覆核仍未完成。197種假設共同平移未翻轉44共同點的誤差排序，第191輪不通過維持不變。詳見[診斷報告](evaluations/post-run191-native-reference-quality.md)。

第191輪完成30epochs／347實測updates，仍未取得合格晉升版本。固定54VAL82TP／1FP／3FN（P98.80%、R96.47%），development淨45TP但44共同／1流失／1新增，定位14scalar退步，完整204比較未執行。新7張14bodylabel實際被抽到487次，但Ares33本來就14全命中，未增加漏檢挑戰。TRAIN153為teacher269TP4FN／selected272TP1FN／末期273TP0FN，這不是泛化證據，未事後改選。權重清理完畢、API九個權重不變；新批次1次完整／347updates／0合格。舊549label路徑未重啟，但其中7張像素以新label副本准入，剩542列像素排除，pretraining仍未抹除。

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


第183輪後：[時序 DEV 選模評估前置驗證](evaluations/round-183-temporal-dev-preflight.md)：41影格／2片段、24序列、984次 tracker updates、1780次神經配對呼叫，零 optimizer。零修正與原生逐欄位一致；固定正向控制改變35影格，雖淨增命中仍有逐序列新增3次身分切換，保守排序判為退步。未證明真正 epoch 選模改善；184尚未啟動，API不變。


第184輪：[逐epoch時序DEV選模完整報告](runs/run-184.md)：30epochs／2,610次實際更新；全部epoch loss、VAL與訪次精確同183，唯一介入為選模。9組時序排序選第1epoch，DEV同原生但pair TP0／FN156、recall0%，未過前置門檻，完整136比較未執行。27個符合pair門檻的epoch仍全有時序退步，最好的22仍6項違反；事後未改選或晉升。[曲線](runs/run-184-learning-curve.json) · [精準度與拒絕](runs/run-184-metrics.json) · [選模診斷](runs/run-184-diagnostics.json)。權重已清理、九個API權重不變；180–189目前5次／13,050updates／零合格。


第184輪後：[TRAIN監督缺口與bbox特徵學習前置驗證](evaluations/round-184-TRAIN-supervision-and-bbox-features-preflight.md)：epoch10／20的已知負配對無高分誤判、已知混合歷史0，未知資料未補成負例。新標準YOLO bbox分支24tensors／639936參數通過特徵梯度／分類隔離RED/GREEN與4TRAIN／10GT原生backward；前置控制零optimizer，非改善證據。新外部素材全部未准入。

第185輪：[bbox特徵學習最終報告](runs/run-185.md) · [固定精準度、所有退步欄位與清理](runs/run-185-metrics.json) · [30epoch vendor學習曲線](runs/run-185-learning-curve.json)。訓練完成但early gate拒絕，完整204比較未執行；API不變。


第185輪後：[定位監督來源稽核與複核原生資料前置驗證](evaluations/round-185-curated-native-supervision-preflight.md) · [數量與來源稽核](evaluations/round-185-curated-native-cohort-audit.json)：原695TRAIN中146張可逐批直接連到後續視覺複核准入，549個較舊列只從新optimizer訪次排除，原檔保留；不宣稱舊標註都錯，亦不抹除pretraining。資料隔離／抽樣RED/GREEN與原生loader/backward通過，前置控制零optimizer。

第186輪：[複核原生監督最終報告](runs/run-186.md) · [精準度、配對定位與實際曝光稽核](runs/run-186-metrics.json) · [30epoch vendor曲線](runs/run-186-learning-curve.json)。整體development誤差下降，但blue微退步、early gate拒絕；完整204比較未執行，不能稱為穩定高速模糊軌跡改善或來源群驗收通過。候選已清理，API不變。


第186輪後：[TRAIN分類訊號診斷與前置驗證](evaluations/round-186-TRAIN-classification-signal-preflight.md) · [TRAIN診斷計數](evaluations/round-186-TRAIN-classification-signal.json)：先封存146raw推論再合併既有259框，4個FN皆有現有IoU框但低class/grid分數，另15未配對；是TRAIN診斷，非獨立驗證。新增6既有分類輸出tensors的梯度／固定state控制通過，前置零optimizer。

第187輪：[聯合分類輸出學習最終報告](runs/run-187.md) · [精準度、全部退步與三項對照](runs/run-187-metrics.json) · [30epoch vendor曲線](runs/run-187-learning-curve.json)。Formal early gate拒絕、完整204比較未執行；TRAIN selected／末期及分類還原皆未產生合格版本。候選已清理、API不變。

第188輪：[紀錄程式錯誤中止報告](runs/run-188.md) · [已知數量、未知更新次數與根因](runs/run-188-metrics.json)。首epoch稽核攔截六個多餘來源路徑；無可驗收權重，未跑精準度或完整軌跡驗收，不算完整訓練，API不變。

第189輪：[分類特徵學習最終報告](runs/run-189.md) · [精準度、全部退步、TRAIN與末期對照](runs/run-189-metrics.json) · [30epoch曲線](runs/run-189-learning-curve.json)。TRAIN改善但固定blue退步；最後epoch亦未泛化，原選擇及拒絕不變。候選清理完畢，API不變。

第189輪後：[四個TRAIN漏檢的原生指派與logit梯度診斷](evaluations/round-189-TRAIN-assignment-diagnostic.md) · [數值證據](evaluations/round-189-TRAIN-assignment-diagnostic.json)。四個目標各10個正向指派／40個向上logit梯度；522單一teacher最佳IoUanchor未被指派，不代表整個目標無正向監督。4CPUforward、0optimizer，非驗證準確率或泛化證據。

第189輪後：[TRAIN座標／分類分數交換前置對照](evaluations/round-189-TRAIN-coordinate-score-swap-preflight.md) · [封存重播數據](evaluations/round-189-TRAIN-coordinate-score-swap-preflight.json)。固定teacher座標仍保留189分數的258／259TP改善，僅換座標仍255TP；7組1022NMS影格、0NN／optimizer。支持測試分離學習，非模型、泛化或未來訓練保證。

第190輪：[分類學習／固定定位最終報告](runs/run-190.md) · [精準度、所有退步與稽核](runs/run-190-metrics.json) · [30epoch曲線](runs/run-190-learning-curve.json)。正式前置拒絕、未跑完整204比較；TRAIN selected258TP1FN14未配對、末期257TP2FN0未配對，未事後改選。候選已清理，API不變。

本批十次完整訓練：[保留與API選擇決策](batches/completed-180-190.md) · [逐輪實測更新與資格](batches/completed-180-190.json)。10次完整、14785updates、0合格／0API；188中止另外記錄且不把未知更新數當零。

第190輪後：[舊素材盤點更正](evaluations/round-190-legacy-native-source-scout.md) · [來源像素與衍生圖稽核](evaluations/round-190-legacy-native-source-scout.json)。原12原圖／原生說法更正為11原生、1linear-motion-blur衍生（第4張）；0label／NN／optimizer／TRAIN准入，未造成訓練曝光。完整外殼、來源與近重複仍待核對，未上傳媒體。

第190輪後補充：[原生來源追溯v2與視角複核](evaluations/round-190-native-source-provenance-v2.md) · [來源別名、衍生排除與計數](evaluations/round-190-native-source-provenance-v2.json)。第二批19原生影格、10內部來源ID對應8標籤（7公開影片身份、1未解析），不等同獨立攝影來源；累計36張不同影像為35原生、1衍生，已知heldout canonical重疊0。0TRAIN准入；使用者已確認完整戰鬥碗／軌道即可、外殼邊角可裁切，191未啟動，190模型拒絕與API不變。

第190輪後素材篩選：[完整戰鬥碗／軌道與攝影背景複核](evaluations/round-190-native-supervision-refresh-screen.md) · [數量與准入限制](evaluations/round-190-native-supervision-refresh-screen.json)。16候選對585唯一參考exact重疊0，但LED8張疑似共用heldout背景而保留；賽事8張只進入新標註提案，0舊label／NN／optimizer／TRAIN准入，191未啟動。

第190輪後：[七張新視覺標註准入研究TRAIN](evaluations/round-190-native-supervision-refresh-admission.md) · [原生載入、資料路由與零optimizer前置控制](evaluations/round-190-native-supervision-refresh-admission.json)。153圖／273框、VAL／TEST原清單不變；新label全部原生讀取精確，回舊label、held／heldout與錯sampler皆紅燈。這是舊來源像素的新標註，非新外部影片、非獨立人工真值，不抹除pretraining。

第191輪：[複核原生監督補充最終報告](runs/run-191.md) · [固定精準度、14退步、逐資料群診斷與實際訪次](runs/run-191-metrics.json) · [30epoch曲線](runs/run-191-learning-curve.json)。正式early gate拒絕，未跑完整204比較；7新TRAIN全部原已命中，273TRAIN漂亮數字未泛化。初次計分舊259sum檢查已修正、只重算封存raw，0新NN／optimizer；best／last清理完畢，API不變。
