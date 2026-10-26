# 第173輪後診斷：因果配對提案的原生對照

173 的完整品質驗收仍失敗。本次只驗證下一輪可能使用的配對機制，**零 optimizer updates、零新權重、零 API 晉升**，不計為第174輪訓練，也不宣稱精準度改善。

模型只提出虛擬位置，用原生 cost、gates 與 solver 再算候選矩陣；不直接寫 native mean/P/R 或速度。只有保留全部 baseline matched pairs、沒有為原本確定的配對新增歧義、且增加無歧義配對或減少既有歧義時才採用。既有濾波器仍僅以實際 detector measurement 更新，confidence／ReID／life-cycle 仍由原生程式判定。

Byte high／low／unconfirmed 的原門檻分別保留0.85／0.5／0.7；high及unconfirmed只做一次原有score fusion，low不融合。新增 pair 還須是 threshold 下該 row／column 的唯一可行邊；Byte guard硬binding及merged排除保留。這是保守准入條件，不是額外放寬原生 gate。

| 檢查 | 實際結果 |
| --- | --- |
| 配對行為 contract | 24項通過，包括既有pair被搶、額外歧義、row／column競爭拒絕及三個Byte門檻 |
| 撤回修正的回歸證據 | 暫時將guard acceptance退回baseline-only，`add safe pair`確實失敗；恢復後24項通過 |
| Reference-blind FIT | 5來源組／170 frames、兩profiles；native／off／zero／固定非零control合計1,360 tracker updates |
| FIT off／zero輸出 | 所有欄位與原生完全一致 |
| 固定非零control | Byte high獲採用3次、改變3個frame/profile輸出；這個control沒有經過訓練，沒有品質結論 |
| 完整固定集 off／zero | 14cases、兩profiles、兩repeats，3,728 tracker updates／1,864 cached-frame visits，所有欄位與凍結Ares33 baseline完全一致 |
| 狀態隔離 | FIT 2,312次、完整固定集5,730次提案期間native狀態陣列核對一致 |
| 工件核對 | 來源封存雜湊及66份輸出重新核對一致 |

兩次回放均無新YOLO推論、沒有讀取實體身分真值。全固定集的zero model只作中性對照；不使用結果選超參數。本地研究採instance-scoped methods，未改產品來源或全域tracker。

這些結果只證明中性相容與機制會運作。新增配對可能改變後續歷史，逐步保留pair不能證明全軌跡非退步；也不能把固定非零control的3次採用當作3次正確配對。正式訓練需另行凍結recipe，仍須通過原本14cases／136比較、所有模糊情境、兩profile、至少兩來源群改善及新的獨立端到端驗收，才可考慮API晉升。

專案檢查：backend398 passed／8 skipped；annotator／beytrack163 passed、coverage94.29%（門檻92%）；UI42 passed、e2e39 passed、UI build與Android unit build成功。pytest最初遭系統temp ACL阻擋；改用新workspace temp後backend通過，annotator另遇export rename拒絕，改用較短新temp路徑後全套通過。保留失敗紀錄，未更改測試或產品程式。

170–179視窗仍是4次實際訓練／4,080 optimizer updates／零合格與零API晉升。持續訓練目標尚未達成。
