## 頻出パターンの発見法
### ３つの重要な指標
1. 支持度（Support）
<br>
<br>
1. 確信度（Confidence）
<br>
<br>
1. リフト（Lift）
---

### 基本的な定義（１）
- $ トランザクション: \begin{align} \quad & 個々の客の1回の買い物 \\\ & （バスケット） \end{align} $ |
<br>
<br>
- $ \Omega: \quad 全トランザクション $ |
<br>
<br>
- $ A: \quad 商品Aの購入を含むトランザクション $ |
---

### 基本的な定義（２）
- $ n( \Omega ): \quad トランザクションの総数（バスケットの総数） $ |
<br>
<br>
- $ n(A): \begin{align} \quad & 商品Aの購入を含むトランザクションの総数 \\\ & （商品Aを含むバスケットの総数）\end{align} $ |
<br>
<br>
- $ n \bigl( A \cap B \bigr) : \begin{align} \quad & 商品Aと商品Bの両方の購入を含む \\\ & トランザクションの総数 \\\ & （商品Aと商品Bの両方を含むバスケットの総数）\end{align} $ |
---

### 基本的な定義（３）
- $ \begin{align} 商品Aが購入される確率: \\\ \qquad P(A) \equiv \frac{n(A)}{n( \Omega )} \end{align} $ |
<br>
<br>
- $ \begin{align} 商品Aと商品Bが同時購入される確率: \\\ \qquad P \bigl( A \cap B \bigr) \equiv \frac{n \bigl( A \cap B \bigr) }{n( \Omega )} \end{align} $ |
---

### 基本的な定義（４）
$ \begin{align} 商品Bを購入しているという条件での、 \\\ 商品Aを購入している条件付き確率 \end{align}: $
<br>
$$ \begin{align} P \bigl( A \; | \; B \bigr) & \equiv \frac{n \bigl( A \cap B \bigr)}{n(B)} \\\ & = \frac{P \bigl( A \cap B \bigr) }{P(B)} \end{align} $$
---

### 基本的な定義（５）
$ A \Rightarrow B: $
<br>
<br>
$$ 「商品Aを購入していると商品Bも購入している」 \\\ というルール（左側を条件部、右側を結論部と呼ぶ） $$
---

### 支持度（１）
$ 商品Aの支持度: $
$$ \begin{align} Supp(A) & \equiv \frac{n(A)}{n(\Omega)} \\\ & = P(A) \end{align} $$
---

### 支持度（２）
$ ルール A \Rightarrow B の支持度: $
$$ \begin{align} Supp \bigl( A \Rightarrow B \bigr) & \equiv \frac{n \bigl( A \cap B \bigr) }{n( \Omega )} \\\ & = P \bigl( A \cap B \bigr) = P \bigl( B \cap A \bigr) \\\ & = \frac{n \bigl( B \cap A \bigr) }{n( \Omega )} \\\ & = Supp \bigl( B \Rightarrow A \bigr) \end{align} $$
---

### 支持度に関する注意点
1. $ Supp \bigl( A \Rightarrow B \bigr) $ は全トランザクションに対して、商品 $ A $ と商品 $ B $ が併売されているトランザクションの比率
1. $ Supp \bigl( A \Rightarrow B \bigr) = Supp \bigl( B \Rightarrow A \bigr) $
1. 支持度が大きいルールを抽出する
    - ほとんど売れていな商品 $ A $ と商品 $ B $ がたまたま同時に買われた様な場合に、そのルールを重要視してしまうことを防ぐ |
    - 支持度が小さいと、たとえルールとして意味があったとしても、ビジネスとしての旨味は少ない |
---

### 確信度
$ ルール A \Rightarrow B の確信度: $
$$ \begin{align} Conf \bigl( A \Rightarrow B \bigr) & \equiv \frac{Supp \bigl( A \Rightarrow B \bigr) }{Supp(A)} \\\ & = \frac{P \bigl( A \cap B \bigr) }{P(A)} \\\ & = P \bigl( B \; | \; A \bigr) \end{align} $$
---

### 確信度に関する注意点
1. $ Conf \bigl( A \Rightarrow B \bigr) $ は、商品 $ A $ が購入されているトランザクションに対して、商品 $ B $ も購入されている（商品 $ A $ と商品 $ B $ が併売されている）トランザクションの比率
1. $ Conf \bigl( A \Rightarrow B \bigr) \neq Conf \bigl( B \Rightarrow A \bigr) $
1. $ Conf \bigl( A \Rightarrow B \bigr) $ が大きいほど、 商品 $ A $ と商品 $ B $ は関連が強いと言える（ただし、上の項目に注意）
1. リフトも見ることが重要
---

### リフト
$ ルール A \Rightarrow B のリフト: $
$$ \begin{align} Lift \bigl( A \Rightarrow B \bigr) & \equiv \frac{Conf \bigl( A \Rightarrow B \bigr) }{Supp(B)} \\\ & = \frac{P \bigl( B \; | \; A \bigr) }{P(B)} \end{align} $$
---

### リフトに関する注意点
1. 単純に商品 $ B $ を購入する割合よりも、商品 $ A $ を購入した中で商品 $ B $ も購入した割合の方が高いとき、リフトは1を超える
1. リフトが1を超えるルールが意味のあるルール
1. $ Lift \bigl( A \Rightarrow B \bigr) \neq Lift \bigl( B \Rightarrow A \bigr) $
1. リフトが大きいルールを抽出することで、商品の関連性によらず売れている商品を除外することができる
