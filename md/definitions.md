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
- $ n( \Omega ): \quad 全トランザクション数（全バスケット数） $ |
<br>
<br>
- $ n(A): \begin{align} \quad & 商品Aの購入を含むトランザクションの総数 \\\ & （商品Aを含むバスケット数）\end{align} $ |
<br>
<br>
- $ n \bigl( A \cap B \bigr) : \begin{align} \quad & 商品Aと商品Bの両方の購入を含む \\\ & トランザクションの総数 \\\ & （商品Aと商品Bの両方を含むバスケット数）\end{align} $ |
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
<br>
$$ P \bigl( B \; | \; A \bigr) \equiv \frac{P \bigl( A \cap B \bigr) }{P(A)} $$
---

### 基本的な定義（５）
$ A \Rightarrow B: $
<br>
<br>
$$ 「商品Aを購入していると商品Bも購入している」というルール \\\ （左側を条件部、右側を結論部と呼ぶ） $$
---

### 支持度（Support）
商品$A$の支持度（$Support$）
\begin{align} Supp(A) & \equiv \frac{n(A)}{n(\Omega)} \\\ & = P(A) \end{align}
<br>
ルール $A => B$ の支持度（$Support$）
$$\begin{align}
Supp(A => B) &= n(A ∩ B) / n(Ω) \\
&= P(A ∩ B) = P(B ∩ A) \\
&= n(B ∩ A) / n(Ω) \\
&= Supp(B => A)
\end{align}$$
<br>
<br>
矢印が付いていますが、Supp(A => B)に方向性はないことに注意しましょう。

Supportが大きいルールを抽出することが必要な理由は、そもそもほとんど売れていな商品Aと商品Bがたまたま同時に買われた様な場合に、そのルールを重要視してしまうことを防ぐためです。

また、Supportが小さいものは、そもそもほとんど売れていないので、たとえルールとして意味があったとしても、それを発見したところでビジネスとしての旨味はないとも考えられます。
