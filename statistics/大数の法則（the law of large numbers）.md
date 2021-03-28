# 大数の法則（the law of large numbers）

- [大数の法則（the law of large numbers）](#大数の法則the-law-of-large-numbers)
  - [独立な確率変数の性質](#独立な確率変数の性質)
  - [大数の法則](#大数の法則)
  - [参考文献](#参考文献)

## 独立な確率変数の性質

2個の確率変数 $X,Y$ において下記が成り立ちます（期待値に関しては独立でない場合においても成り立ちます）。

期待値：

$$E(X + Y) = E(X) + E(Y)$$

分散：

$$Var(X + Y) = Var(X) + Var(Y)$$

また、 $n$ 個の確率変数においても下記が成り立ちます。

期待値：

$$E(X_1 + X_2 + \cdots + X_n) = E(X_1) + E(X_2) + \cdots + E(X_n)$$

分散：

$$Var(X_1 + X_2 + \cdots + X_n) = Var(X_1) + Var(X_2) + \cdots + Var(X_n)$$

そのほか、同一の確率分布に従っている場合、次のことがいえます。

期待値：

$$E(X_1) = E(X_2) = \cdots = E(X_n) = \mu$$

分散：

$$Var(X_1) = Var(X_2) = \cdots = Var(X_n) = \sigma^2$$

同一の確率分布に従っているので、期待値はすべて $\mu$ になり、分散はすべて $\sigma^2$ になるということを表しています。

このとき

期待値：

$$\begin{aligned}
& E(X_1 + X_2 + \cdots + X_n)
\\
=~& E(X_1) + E(X_2) + \cdots + E(X_n)
\\
=~& \mu + \mu + \dots + \mu
\\
=~& n\mu
\end{aligned}$$

分散：

$$\begin{aligned}
& Var(X_1 + X_2 + \cdots + X_n)
\\
=~& Var(X_1) + Var(X_2) + \cdots + Var(X_n)
\\
=~& \sigma^2 + \sigma^2 + \cdots + \sigma^2
\\
=~& n\sigma^2
\end{aligned}$$

となります。これらをふまえて、平均 $\bar{X}$ について考えますと

$\bar{X}$ の期待値：

$$\begin{aligned}
E(\bar{X}) &= E\left[\frac{1}{n}(X_1 + X_2 + \cdots + X_n)\right]
\\
&= \frac{1}{n}E(X_1 + X_2 + \cdots + X_n)
\\
&= \frac{1}{n} \cdot n\mu
\\
&= \mu
\end{aligned}$$

$\bar{X}$ の分散：

$$\begin{aligned}
Var(\bar{X}) &= Var\left[\frac{1}{n}(X_1 + X_2 + \cdots + X_n)\right]
\\
&= \frac{1}{n^2}Var(X_1 + X_2 + \cdots + X_n)
\\
&= \frac{1}{n^2} \cdot n\sigma^2
\\
&= \frac{\sigma^2}{n}
\end{aligned}$$

## 大数の法則

チェビシェフの不等式を用いて証明します。

チェビシェフの不等式を用いれば、どのような確率分布に従う確率変数においても成り立つことが示せます。


$X=\bar{X}$ （ $n$ 個の確率変数の平均）とおくと
$$E(\bar{X})=\mu,Var(\bar{X})=\dfrac{\sigma^2}{n}$$
となります。

また、標準偏差は
$$D(\bar{X}) = \sqrt{\dfrac{\sigma^2}{n}} = \dfrac{\sigma}{\sqrt{n}}$$
となります。

チェビシェフの不等式は

$$
P\left( |X-\mu| \geq k\sigma\right) \leq \frac{1}{k^2}
$$

であり

$$
P\left( |\bar{X}-\mu| \geq k \dfrac{\sigma}{\sqrt{n}} \right) \leq \frac{1}{k^2}
$$

が得られます。

ここで $k\dfrac{\sigma}{\sqrt{n}}=\epsilon$ とおくと $k=\dfrac{\epsilon\sqrt{n}}{\sigma}$ です。

これより、

$$\begin{gathered}
\Leftrightarrow P\left( |\bar{X}-\mu| \geq \epsilon\right) \leq \frac{1}{ \left( \dfrac{\epsilon\sqrt{n}}{\sigma} \right)^2}
\\
\Leftrightarrow P\left( |\bar{X}-\mu| \geq \epsilon\right) \leq \frac{1}{ \dfrac{\epsilon^2n}{\sigma^2} }
\\
\Leftrightarrow P\left( |\bar{X}-\mu| \geq \epsilon\right) \leq \frac{\sigma^2}{\epsilon^2n}
\end{gathered}$$

となります。

したがって、任意の $\epsilon > 0$ において

$$
P\left( |\bar{X}-\mu| \geq \epsilon\right) \leq \frac{\sigma^2}{\epsilon^2n} \rightarrow 0 \quad (n\rightarrow\infty)
$$

が示されます。

このとき $\bar{X}$ は $\mu$ に確率収束すると呼びます。


## 参考文献

- 東京大学教養学部統計学教室『統計学入門 (基礎統計学Ⅰ) (日本語) 単行本 – 1991/7/9』