# DistilBERT Classification
這個專案為一部份的碩論實驗，為 Initialization、Training & Inference 的實驗。
實驗分成兩種：Feature-based 和 E2E-based
### Feature-based
先在 /Feature-based/SessMLM_training.ipynb 對 pre-trained DistilBERT 使用 Session data MLM 進行 further pre-training之後，用 further pre-trained 模型輸出資料集中每個 Session data 的 embedding，再於 /Feature-based/classification.ipynb 訓練 4 種 classifiers 得到每個月的 Accuracy 和 F1 Macro。

### E2E-based
先在 /E2E-based/SessMLM_finetuning.ipynb 載入在 Feature-based further pre-trained 模型當作是 DistilBERT 的初始權重，並在後面接上設計好的 classifier layers，訓練時整個模型一起訓練 (DistilBERT + classifier layer)，再於 /E2E-based/classification.ipynb 得到每個月的 Accuracy 和 F1 Macro。
