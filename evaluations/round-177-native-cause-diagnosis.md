# 第177輪後：Kalman沒有改善的原生原因診斷

這不是第178輪或新的訓練，也不是新的品質驗收。只分析既有177輸出，另做有界、reference-blind的原生因果記錄；零optimizer、零NN forward、零新YOLO推論、零API變更。177仍拒絕。

## 原固定集 primary coverage 分解

只取14cases各一次、repeat0／scenario0／24px，各profile796 reference entries，案例可能重疊，非796個獨立實拍樣本。原生Kalman TP708／FN88，其中FN：71個有高信心sensor候選、12個無24px內sensor、5個只有低信心sensor。137個已量測點為observed但identity_uncertain，另40個是tentative；這些不冒充certain。

## 直接記錄原生決策

逐一原生回放兩profile：932 tracker updates、466 cached-frame visits、14 exports，**所有輸出欄位與封存基準完全一致**。記錄成本矩陣、merged pool與原生ReID實際呼叫；封存後才連結參考，沒有修改任何state、gate、flag或identity。

71個Kalman強sensor漏點中：57個對所有nonmerged track的成本均為無限，當中44個全部因Mahalanobis gate拒絕；另8個有可用有限成本但被競爭配對排除、5個所有既有track被merged保護、1個在birth前無既有track。絕對gate亦有3個all-row拒絕條件，可能與其他原因重疊。

137個observed-uncertain reference hits中：115個原生own-appearance distance過高、112個與競爭anchor區分度不足、32個pixel可靠度不足、32個競爭anchor可靠度不足；**同一點可能多個條件失敗，不能相加成總量**。另外3個當下配對歧義、1個已通過當下ReID evidence但尚未累積3次。這說明現有appearance/ReID與motion gate是不同瓶頸，不可把學到較高pair分數直接改成certain。

Byte的231個強sensor漏點中，229個對所有nonmerged guard rows有原生Byte ID binding不符；這是Byte core／guard銜接的實際拒絕條件，不是授權繞過binding。

後續實驗只針對TRAIN缺少hard positive的motion部分，用明確標示的合成預測誤差壓力測試，保持原生ReID、身份與全部驗收要求。此診斷不證明它會改善；完整新模型仍須獨立驗證。

[結構化逐案例原因與全部計數](round-177-native-cause-diagnosis.json)。原六案例仍missing/unverified，等效參考是助理複核、不是獨立人工真值。
