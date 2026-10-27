# 第184輪後：TRAIN監督缺口與bbox特徵學習前置驗證

最新完成訓練仍為184；以下所有診斷與機制控制均為0 optimizer updates，不是185輪或新準確率。

## TRAIN封存診斷

僅合併184輪epoch10／20已封存的真正當前模型TRAIN配對與原有身分參考，沒有新推論，也未分析VAL／完整驗收來產生訓練目標。所有原始封存、來源程式與參考SHA逐一核對。

| 指標 | epoch10 | epoch20 |
| --- | ---: | ---: |
| 已知且同一身分的歷史配對呼叫 | 3730 | 3736 |
| 歷史含未知身分 | 109 | 109 |
| 已知混合身分歷史 | 0 | 0 |
| 未知歷史得到≥0.95分數 | 47 | 48 |
| 已知負配對得到≥0.95分數 | 0 | 0 |
| 未知／混合／候選未知而排除配對監督 | 124 | 125 |

這些數字是pair-call暴露，並非獨立樣本。不能因未知歷史得到高分，就把未知物體補成負例。既有TRAIN沒有已知混合歷史，無法為「歷史有效性」分支提供已知負類；因此未建立或訓練該分支。這項診斷不能外推為未標註配對都正確。

## 回到實際偵測器的定位特徵學習

175只更新YOLO bbox最後6個tensors／12,480參數。新的前置機制開放既有三個bbox分支內的特徵卷積及BN affine，共24tensors／639,936參數；backbone／neck、分類分支、DFL basis與所有BN running statistics固定。架構與推論仍為標準YOLO，不修改tracker門檻。

實際控制：擾動bbox特徵卷積會改變boxes，raw與decoded class scores逐欄位精確相同；合成backward得到有限非零特徵梯度，所有state在backward後保持相同，optimizer擁有權精確、memory-only half checkpoint的475個固定state精確相同。改回舊tail-only政策時，特徵梯度測試實際變紅；放開分類分支時，分類隔離測試實際變紅。沒有執行optimizer step。

另核對既有695TRAIN／54VAL／47TEST、1,592個檔案引用與現有split／固定驗收隔離。預先選定4張TRAIN圖／10個GT的GPU原生vendor loss backward有24個gradient tensors、16個非零，其中4個為bbox特徵卷積；所有梯度有限，固定state未變。這只證明新訓練路徑可學習，尚未證明高速、模糊或定位改善。

保留限制：既有標註不是獨立人工真值，110張空間模糊資料是合成，歷史pretraining是否排除固定驗收仍未證實。下一個實際訓練必須維持原有early gate與完整204比較／至少兩來源兩profile改善，並另有獨立端到端驗收，才可能晉升API。

## 素材篩選

查閱兩個公開標示CC BY4.0的資料集並各視覺檢查一張匿名預覽：[Beyblade v5](https://universe.roboflow.com/beyblade-djcpy/beyblade-dtd3d/dataset/5)、[Beyblade X Dataset](https://universe.roboflow.com/beyblade-arupe/beyblade-x-dataset)。前者紅盤視角傾斜且外殼裁切；後者黃X盤近上方拍攝，但外殼完整入鏡仍未確認，且缺少已核實時間戳／影片來源。都未准入任何訓練或驗收；沒有下載全部資料、登入或繞過匿名預覽限制。未以單張樣本判定整個資料集都不合格。

API九個既有權重未變，尚無新合格版本或希臘名稱。
