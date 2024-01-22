# Colabの使い方
## ファイルのインポート

```
import CSV
csvfile = open('/content/drive/My Drive/data.csv', 'r', encording='utf-8')
```

## Pythonの基本文法
```
for 変数名 in オブジェクト:
    '処理'
```
```
for文の繰り返し
names = ['太朗', '次郎','三郎']
for name in names:
    print(name)

結果　太朗
    次郎
    三郎
```

```
while文の繰り返し処理
i = 0

while i < 3:
    print(i)
    i += 1

結果
    0
    1
    2
```
```
変数num1を定義して、num1に8を代入して、表示
変数num2を定義して、num2に4を代入して、表示
num1 = 8
print( num1 )

8

num2 = 4
print( num2 )

4

```

```
変数num1とnum2の和差積商を求めて表示

num1 + num2
12

num1 - num2
4

num1 * num2
32

num1 / num2
2.0
```


```
データの表示
data.tail()で表示し確認できる

 import pandas as pd

 data = pd.read_csv('./data.csv')

 data.tail()
```

```
データの状態を確認できる
data.shape
(行数,列数)

data.locで行列の中身を取得できる
data.loc[行,列]

data.ilocで行番号と列番号を指定してデータを取得。
（例）data変数の中で2行目と3行目且つ0列目と1列目を表示
data.iloc[1:3, [0,1]]

```

```
データの整形
data.sort_values()で、値を参照して並び替える事ができる
data.sort_index()で、インデックスを参照して並び替える事ができる

```


```
data.isnullで全てのデータの欠損状態を確認する事ができる
data.dropna()で欠損値を削除する事ができる
欠損値に値を挿入する時は、data.fillna()を使用します。

```

##pythonに慣れる (pandas)

```
data変数のデータ形式を表示

type(data)
データ形式の表示が反映
```

```
pandasでSeries型データを作成して、データ形式を確認

Series = pd.Series([1,3,5])
type(Series)

```

```
data変数の上から(数字)行表示

data.head(数字)
表があればその上から数えた数字を表示

data変数の下から(数字)行表示

data.tail(数字)
表があればその下から数えた数字を表示
```

```
data変数のカラムを表示
data.columns

data変数のインデックスを表示
data.index

data変数の各カラムのdata型を表示
data.dtypes

data変数の各カラムのユニーク数を表示
data.nunique()

data変数の各インデックスのユニーク数を表示
data.nunique(axis=1)

```

```
data変数の上から4行目のデータを表示
data.loc[3,:]

data変数の中で国語が70点以上の人を表示
data[data['国語'] >= 70]

data変数の中で数学が30点未満の人を表示
data[data['数学'] < 30]

data変数の中で国語が60点ピッタリの人が何人いるか表示
len(data[data['国語'] == 60])

data変数の中で数学が50点以上の人が何人いるか表示
len(data[data['数学'] >= 50])

len　は〜〜で何人いるのかを表示したい場合に使用

data変数の中で国語の点数が1番高い人を表示
data[data['国語'] == data['国語'].max()]['name']

data変数の中で全ての人の国語の点数を表示
data,loc[:,'国語']

data変数の中で全ての人の国語と数学の点数を表示
data[['国語','数学']]

data変数のカラムの情報を確認
data.info()

dataの下にe_dataを連結させて下さい。中身を表示さしたい場合はdataを
data = pd.concat([data,e_data],axis=0,sort=True)
data

dataのindexを振り直し
data = data.reset_index()
data.drop(['index'],axis=1, inplace=True)
data

dataの各カラムの合計値を表示
data.sum()

dataの各行の合計値(sum)を表示
data.sum(axis=1)

dataの各行の平均値(mean)を表示
data.mean(axis=1)

data変数のカラムの統計量を算出
data.describe().round(1)

data変数の中の各カラムの相関係数(corr)を算出
data.corr()

data変数の中で数学カラムの中に重複がないことを確認
len(data) == len(data['数学'].nunique())

data変数の中で国語の点数が60点の人が3人います。重複レコードを削除
data[~data['国語'].duplicated()]

名前の行に重複が見られます。その行を削除(drop)
data_2.drop_duplicates('name' ,inplace=True)
data_2

```

```
欠損値がある行を表示して下さい
data_2.loc[data_2.isnull().any( axis = 1), :]



DataFrame()
データフレームワークの新規作成
例文
 importし pandas をpdという名前で使用できるようにします。
import pandas as pd
 pandasのDataFrame関数を呼び出し
df = pd.DataFrame({'国語': [90, 60, 70:]})

to_csv()
データフレームをファイルに出力

read_csv()
csvやtextファイルのデータをデータフレームに読み込み。

例pd.read_csv('/content/drive/MyDrive/a.csv')

merge
データフレーム同士をマージ。
共通の列を持つデータフレーム同士を結合したい時。

values
特定の列データをarray型で取得。列のデータをarray形で受け取りたい時。


```