# DistilBERT Classification
這個專案為一部份的碩論實驗，為 Initialization、Training & Inference 的實驗。
實驗分成兩種訓練模式：Feature-based 和 E2E-based。
### Feature-based
在 `/Feature-based/SessMLM_training.ipynb` 中，先對預訓練的 DistilBERT 模型使用 Session data 進行 MLM 的 further pre-training。完成 further pre-training 後，使用該模型輸出資料集中每個 Session data 的嵌入（embedding）。接著，在 `/Feature-based/classification.ipynb` 中使用這些嵌入訓練四種分類器，並計算每個月的 Accuracy 和 F1 Macro。

### E2E-based
在 `/E2E-based/SessMLM_finetuning.ipynb` 中，載入在 Feature-based 中已 further pre-trained 的模型作為 DistilBERT 的初始權重，並接上設計好的分類層（classifier layers）。訓練時，整個模型（DistilBERT + classifier layers）將一起進行訓練 (微調)。完成後，在 `/E2E-based/classification.ipynb` 中計算每個月的 Accuracy 和 F1 Macro。
