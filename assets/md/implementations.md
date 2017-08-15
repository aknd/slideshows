### アソシエーションルールの抽出

```R
> library(arules)
> library(dplyr)
> data(Groceries)
> rules <- apriori(Groceries,
                   parameter=list(support=0.005,
                                  confidence=0.3,
                                  minlen=2,
                                  maxlen=2))
> subrules <- rules %>%
    subset(lift > 2) %>%
    sort(by=c('lift', 'confidence', 'support'))
> subrules %>%
    head %>%
    inspect
```
@[1](パッケージarulesを読み込む)
@[2](パッケージdplyrを読み込む)
@[3](arulesのサンプルデータGroceriesを読み込む)
@[4-8](関数aprioriでルールを抽出)
@[4](トランザクションデータ)
@[5](支持度（Support）の最小値)
@[6](確信度（Confidence）の最小値)
@[7](ルールに含まれる商品の数の最小値)
@[8](ルールに含まれる商品の数の最大値)
@[9-11](リフト（Lift）で絞り込み・並べ替え)
@[9](rulesをパイプ演算子で次のsubsetに渡す)
@[10](リフトが2より大きいものに絞り込み)
@[11](リフト・確信度・支持度で降順に並べ替え)
@[12-14](ルールの確認)
@[12](subrulesをパイプ演算子で次のheadに渡す)
@[13](最初の方だけ取り出す)
@[14](中身を確認)
---

### 出力結果
---?img=assets/img/plot.png
