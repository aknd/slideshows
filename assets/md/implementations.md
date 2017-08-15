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
