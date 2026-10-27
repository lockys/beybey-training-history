# 第186輪後：TRAIN分類訊號診斷與分類輸出學習前置驗證

186完成347updates但early gate未通過，候選已清理。本次診斷與機制控制均0optimizer，不計第187輪或驗證改善。

## 先封存，再合併標註

只對既有146張複核TRAIN影格，用保護Ares33做146次全新raw推論；所有decoded框、class scores、固定feature-grid座標與NMS輸出先封存，再由另一支程式讀取原有259個本體框。無VAL／TEST／development／完整驗收推論，未修改任何標註、門檻或API。推論前後model state與來源SHA相同，network guard外連0。

固定640-square letterbox／RGB／float32、confidence0.35、NMS IoU0.5、GT IoU0.5。相對259個助理複核本體框，NMS結果為TP255／FN4／未配對輸出15；8張empty的FP0。全部4個FN與15個未配對輸出均來自組裝狀態那批TRAIN，其餘三批共187框均有匹配。這是TRAIN診斷，不能當作驗證準確率。

四個漏框都有IoU≥0.5的raw候選，但最高class score約0.127／0.150／0.001／0.202，固定grid-center的最高分也低於0.35。沒有證據指向這四例的NMS／一對一指派競爭。15個未配對輸出分布於15影格，與GT最大IoU均0、分數0.366–0.863；它們只是在既有組裝本體標註定義下未配對，不是獨立人工認定的誤報。

以上支持檢驗分類學習，但不是「所有問題只有分類」的因果證明：bbox變更也可能把不同分數的anchor移到目標附近。640-square輸入亦不等同所有runtime矩形設定，不外推物理速度或完整軌跡品質。

## 新的標準架構內學習介入

相對186，保留24個bbox特徵tensors／639936參數，新增三個既有Conv2d128→1分類輸出層weight／bias，共6tensors／387參數可訓練；合計30tensors／640323參數。backbone／neck、分類特徵卷積、DFL basis與所有BN running statistics固定，469個其他state不更新。架構與推論、confidence／NMS／tracker門檻不變，沒有手動放大分數。

合成機制控制證實：只擾動分類輸出時scores改變、boxes逐欄位相同；只擾動bbox特徵時boxes改變、scores逐欄位相同。兩條梯度路徑有限非零、固定backbone無梯度，backward前後state相同；optimizer擁有權精確、memory-only half checkpoint的469固定state精確相同。改回box-only政策，分類學習測試實際變紅；放開backbone，固定梯度測試實際變紅。未執行optimizer step。

原生4張TRAIN／10GT backward得到30個gradient tensors、22個非零，含4個bbox特徵卷積與6個分類輸出；全部有限、state未變，optimizer實例／更新均0。146TRAIN／259框／8empty、54VAL／85框與494引用重新核對。這只證明新訓練路徑能學習，尚未證明品質提升。

後續187從保護Ares33初始化，沿用146資料、五層695draws/epoch、30epochs／5220batches／20850訪次與同樣AdamW配方，best只依vendor VAL fitness。原154fresh-predict early gate、204完整比較／至少兩來源兩profile改善與獨立端到端資格不變。所有標註仍非獨立人工真值，cohort不能抹除繼承的pretraining；未准入新外部素材，未產生新pseudo-label或提前晉升API。
