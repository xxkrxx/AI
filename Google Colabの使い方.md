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