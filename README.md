# kaggle-bank-marketing
"Kaggle Bank Marketing Binary Classification Challenge"

このリポジトリでは、Kaggleの銀行データセットを用いて**顧客が定期預金を申し込むかどうかを予測するモデル**の構築を行なった。
初めてのコンペでの作品


---
##  概要
- **課題タイプ**：二値分類（binary classification）
- **評価指標**：ROC AUC（曲線下面積）
- **使用モデル**：LightGBM（勾配ブースティング決定木）
- **主な処理**：前処理、特徴量エンジニアリング、欠損値処理、ワンホットエンコーディング

---
##  課題内容

銀行が行ったマーケティング活動の履歴データから、  
「その顧客が定期預金に加入するか (`y` = yes or no)」を予測する問題です。

---
##  ファイル構成

| ファイル名               | 内容                                 |
|--------------------------|--------------------------------------|
| `bank_model.ipynb`       | 前処理・学習・予測までを含むメインノートブック |
| `submission.csv`         | Kaggle提出用ファイル（予測結果）     |
| `README.md`              | このプロジェクトの説明ファイル       |

---
##  使用技術・ライブラリ

- Python（3.8）
- pandas / numpy / matplotlib / seaborn
- scikit-learn
- LightGBM
- Jupyter Notebook

---
##  モデル概要とスコア

- 最終モデル：`LightGBMClassifier`
- 公開スコア（Public LB）：**0.95962**
- 上位スコアの目安：**0.97前後**

---

##  工夫したポイント

- `job`, `education`, `month` などのカテゴリ変数をグループ化・ワンホットエンコーディング
- `month` から「上半期・下半期（half_year）」という新しい特徴量を作成
- `poutcome`（前回のキャンペーン結果）を success / その他 にまとめて二値化
- `contact` や `day` は情報が少ないと判断し、ドロップ

---

##  実行方法（ローカル or Colab）

```bash
jupyter notebook bank_model.ipynb

---
