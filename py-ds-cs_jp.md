# Python Data-science Cheat-sheet [JP]

## 前処理

### 読み込み

```python
### Read data
data_path = '../data/ssdse/modified/SSDSE-A-2024-2019.csv'
df_raw = pd.read_csv(data_path, encoding='utf-8')
```
<details>
<summary>パラメータ</summary>

* `encoding`：文字コードの指定（`'shift_jis'`や`'utf-8'`）

</details>

### 加工

#### 削除
カラムの確認
```python
### Check columns
df_raw.columns
```
削除
```python
### Set unnecessary columns
drop_columns = ['都道府県', '市区町村']

### Drop unnecessary columns
df = df_raw.drop(columns=drop_columns)
```

#### データ型変換
データ型の確認
```python
### Check the data types
df_raw.info()
```
データ型の変換
```python
### Set the numeric columns
numeric_columns = ['地域コード', '都道府県', '市区町村']

### Copy data-frame
df = df_raw.copy()

### Convert object to numeric(float64)
df[numeric_columns] = df[numeric_columns].astype(np.float64)
```

#### 結合
```python
### Merge the data-frames
df = pd.merge(df1, df2, on='地域コード')

### Check the data frame
df.info()
```
<details>
<summary>パラメータ</summary>

* `on`：結合のキーとなる列のカラム名

</details>

#### ダミー変数化
#### 標準化
#### 主成分分析
### 集計
### 可視化
### 解釈

## 学習
### データ分割
#### ホールドアウト法
#### k分割交差法
### ハイパーパラメータ探索
#### グリッドサーチ
### 回帰アルゴリズム
#### 線形回帰
#### 回帰木
#### ランダムフォレスト
#### 勾配ブースティング決定木
### 分類アルゴリズム
#### ロジスティック回帰
#### 決定木
#### ランダムフォレスト
#### 勾配ブースティング決定木

## 評価
### 回帰評価指標
#### RMSE/MAE/MAPE
#### 決定係数
### 分類評価指標
#### 混同行列
#### 正解率/適合率/再現率/F値
#### マイクロ平均/マイクロ平均
#### ROC曲線

## 学習（教師なし）
### クラスタリング
### 異常検知