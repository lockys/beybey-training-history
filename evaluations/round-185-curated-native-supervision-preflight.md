# 第185輪後：定位監督來源稽核與複核原生資料對照

185已完成30epochs／347updates，early定位非退步門檻失敗且權重清理。本次資料稽核、抽樣控制與backward均0optimizer，不計新訓練或品質改善。

目前695TRAIN的來源鏈包含早期manifest的 llm_pseudo_label_experiment／unreviewed_llm_labels_not_ground_truth 標記，及後來四批明確視覺複核准入。保守可追溯子集為146影格／259個組裝本體框／8張empty，連到當時的admission、參考、兩輪視覺複核與label SHA。四批都是同一助理複核，沒有獨立人工真值；不把四批視為四個獨立攝影來源。

| 准入批次 | TRAIN影格 | 本體框 |
| --- | ---: | ---: |
| v1組裝狀態／空盤 | 56 | 72 |
| v2原生白色陀螺 | 42 | 84 |
| v3白盤補充 | 41 | 82 |
| v4灰盤補充 | 7 | 21 |
| 合計 | 146 | 259 |

新監督子集排除549個較舊TRAIN列，原始檔全部保留。它們的歷史metadata為531個llm/pending、15個source缺漏/pending、3個llm/cross-reviewed-pending-human。這些metadata不證明標註都錯誤，也不能排除另有歷史修訂；本實驗只採用四批可直接核對的新准入來源。Ares33仍可能繼承更早的資料，縮小本輪監督不能抹除pretraining或證明來源獨立。

## 隔離與行為控制

原695TRAIN／54VAL／47TEST的1,592檔案引用均核對SHA，四批admission manifest及參考／複核hash均核對。新路徑清單只引用原有圖片／標註，沒有新pseudo-label、修改框或複製圖片。54VAL／47TEST清單逐bytes相同，TRAIN與heldout／既有固定驗收的精確影像交集0；歷史pretraining排除仍未證實。注入一個舊cohort列或heldout列，檢查均實際變紅；正確子集通過。

沿用五層mass：hard25%、empty20%、white20%、gray5%、easy30%；篩選後分別6／8／41／7／84張。每epoch仍695次replacement draws、seed47，30epochs仍預計5,220batches／20,850訪次。這是146張的重播，不是新增695張；cohort與層內曝光分布都改變，不能把後續差異只歸因標註品質。

舊695-image-only sampler對146影像的測試實際變紅；改成uniform時，原mass行為測試變紅。正確sampler的80個模擬epoch／55,600draws逐次seed重播一致，實測各層比例25.22%／19.98%／20.06%／4.82%／29.92%，符合預定容差；這80個模擬epoch沒有optimizer，不計訓練。

## 原生YOLO載入與梯度

實際loader驗證146TRAIN／259框／8empty及54VAL／85框，494引用核對。只取四張預定TRAIN／10GT做GPU原生loss backward：24個gradient tensors、16個非零，其中4個為bbox特徵卷積；所有梯度有限，分類autograd停用，backward前後state精確相同，optimizer實例與更新均0。

後續186使用同185的標準YOLO bbox特徵分支24tensors／639936參數、固定475states／分類／BNstatistics、同一訓練與draw預算，從保護Ares33初始化。新外部素材仍未准入。best只依vendor VAL fitness，原154fresh-predict early gate、完整204比較／至少兩來源兩profile改善及獨立端到端API驗收不變。這份前置證據不代表高速模糊軌跡已改善。
