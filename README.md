# 線形重回帰モデル
## 目的変数
- CEFR: {"A1": 1, "A2": 2, "B1": 3, "B2": 4, "C1": 5, "C2": 6}

## 説明変数
1. Average Sentence Length in a Single Document（単一ドキュメントにおける文長（＝単語数）の平均）
2. ドキュメント内の単語における pre school level の割合
3. ドキュメント内の単語における elementary school level の割合
4. ドキュメント内の単語における secondary school level の割合
5. ドキュメント内の単語における high school level の割合
6. ドキュメント内の単語における academic level の割合
7. ドキュメント内の単語における unknown の割合（分類不可）

## Jupyter Notebookの流れ
1. cefr_leveled_texts.csvに入っている約1500レコードの（text, CEFR）を教師データとして読み込む．
2. 教師データのtextから7つの説明変数を生成する．
3. 教師データを，訓練用と検証用に8:2に分割する．
4. 訓練データにおいてMean Squared Errorが最小となるように，各説明変数の係数 model.coef_ を学習させる．
5. 学習済みモデルを検証データを使って評価する．この評価が良くなるように説明変数を削ったり足したりする．
6. 改善が終わったらgroup_work_text.csvの10ドキュメントのreadabilityを算出して終了．

## Jupyter Notebook Workflow
1. Load approximately 1500 records of (text, CEFR) from cefr_leveled_texts.csv as 教師 data.
2. Generate seven explanatory variables from the text in the 教師 data.
3. Split the 教師 data into training and validation sets in an 8:2 ratio.
4. Train the coefficients model.coef_ for each explanatory variable to minimize the Mean Squared Error on the training data.
5. Evaluate the trained model using the validation data. Add or remove explanatory variables to improve this evaluation.
6. Once improvements are complete, calculate the readability of the 10 documents in group_work_text.csv and finish.
