# 第178輪後：有證據的整組配對替換 preflight

零optimizer、零API變更，這不是新訓練或品質驗收。178維持拒絕。

已封存原生矩陣顯示：71個Kalman強sensor漏點中38個發生於兩個既有track rows都已配對（30個全候選cost無限、8個有有限競爭cost）。舊研究採用規則永遠保留所有舊row→column，所以這些時刻無法替換任何舊配對。這只證明限制，不證明NN會正確評分或新規則有改善。

新的研究規則只允許高／低雙向證據的整組採用：降低cost必須p≥.95，提升cost只能是p≤.05的無限veto；每個舊已配對row都須繼續配對，替換需舊p≤.05且新p≥.95。未知、中間或無效分數不能證明替換。Guard維持原生global ambiguity判斷，禁止新／改配對歧義與既有無歧義row變歧義；Byte high/unconfirmed的每個新／改配對必須是row及column唯一可用選項。low、Byte guard／ID binding、所有原生ReID／confidence／life-cycle／quality／merged／absolute gates不改，也不直接寫mean/P/R或certain flag。

16項行為控制通過；還原舊selector確實在「全rows已配對仍可採用雙向證據替代」變紅。另抓到float32把實際略高於.05／略低於.95的分數四捨五入後誤認合格，改以float64保留runtime Python-float語意；邊界紅→綠與全部16項再驗均通過，保留初版與失敗證據。

FIT native／off／zero／固定正負control共1,700次updates，中性與停用逐欄位一致；2,074組中性模型輸入bit-exact，實際執行1,706個negative-veto提案，固定正control4次matrix採用。完整14case off／zero、兩profile、兩重播共3,728次updates逐欄位一致，保留原native invalid-geometry withhold。合成live control確實替換2個既有配對並保留2個row；**這只是機制控制，不是身份或軌跡改善**。

179若執行，會重現178的相同分類器訓練配方並核對每epoch loss／validation，以隔離runtime採用規則；舊178權重已清理，不能冒稱續訓。實際optimizer如實計數，但不稱獨立新表示或新增實拍來源。完整非退步、兩profile至少兩來源、原所有模糊情境／敏感度／重播、產品整合與API門檻均不降低。並保留所有pair scalar scores供後續有界診斷，失敗後仍立即清理權重。

[結構化全部控制與雜湊](round-178-certified-replacement-preflight.json)。
