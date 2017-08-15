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
@[3](arulesのサンプルデータGroceries（食料品の販売データ）を読み込む)
