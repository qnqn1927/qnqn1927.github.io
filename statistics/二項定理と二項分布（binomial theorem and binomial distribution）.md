# 二項定理と二項分布（binomial theorem and binomial distribution）

- [二項定理と二項分布（binomial theorem and binomial distribution）](#二項定理と二項分布binomial-theorem-and-binomial-distribution)
  - [二項定理](#二項定理)
  - [ベルヌーイ試行と二項分布](#ベルヌーイ試行と二項分布)
    - [$(1)$ の証明](#1-の証明)
    - [$(2)$ の証明](#2-の証明)

## 二項定理

下記の数式で表される定理のことです。

$$
\begin{aligned}
& \left( x+a\right) ^{n}\\[5px]
=& {}_n\mathrm{C}_{0}x^{0}a^{n}+{}_n\mathrm{C}_{1}x^{1}a^{n-1}\cdots{}_n\mathrm{C}_{n}x^{n}a^{0}\\[5px]
=& \sum ^{n}_{k=0}{}_n\mathrm{C}_{k}x^{k}a^{n-k}
\end{aligned}
$$

これは各項の係数が組合せの公式 ${}_n\mathrm{C}_{k}$ に従うことを示しています。

## ベルヌーイ試行と二項分布

以下が成り立つとき、これをベルヌーイ試行と呼びます。

- 一度の試行で「成功・失敗」のように2種類の事象だけが生じる
- これらの事象が独立
- これらの事象の確率が常に一定

コイン投げで考えます。

「表：1、裏：0」として、5回の試行について $x$ 回の表が出る確率は

$$
f(x) = {}_5\mathrm{C}_x(\frac{1}{2})^5
$$

となります。

あることの生じる確率が $p$ 、その回数を $x$ 回として一般化しますと

$$
f(x) = {}_n\mathrm{C}_xp^{x}(1-p)^{n-x}
$$

となります。

この確率を二項分布と呼び、
$$Bi(n,p)$$
で表します。

そのほか、二項定理および $q = (1-p)$ より

$$\begin{aligned}
\sum^{n}_{x=0}{}_n\mathrm{C}_xp^{x}(1-p)^{n-x} &= (p+q)^n
\\
&= \{p+(1-p)\}^n
\\
&= 1^n
\\
&= 1
\end{aligned}$$

と示すことができます。全確率が $1$ で、規格化の条件を満たしていることがわかります。

いま確率変数 $X$ が二項分布に従っているのであれば期待値、分数はそれぞれ

$$
\begin{aligned}
E(X) &= np &\quad&(1)\\
V(X) &= np(1-p) &&(2)\\
\end{aligned}
$$

となります。

### $(1)$ の証明

期待値は「とり得る値すべてにおける値とその確率の掛け合わせの総和」であるので、

$$\begin{aligned}
E\left( X\right) &= \sum ^{n}_{x=0}x \cdot {}_{n}\mathrm{C}_{x}p^{x}q^{n-x}
\\
&= 0{}_n\mathrm{C}_0 p^{0}q^{n-0} + \sum ^{n}_{ {\color{red}x=1}}x \cdot {}_{n}\mathrm{C}_{x}p^{x}q^{n-x}
\\
&= {\color{red}0} + \sum ^{n}_{x=1}x \cdot {}_{n}\mathrm{C}_{x}p^{x}q^{n-x}
\\
&= \sum ^{n}_{x=1} {\color{red}n} \cdot {}_{n-1}\mathrm{C}_{x-1} \cdot {\color{red}p} \cdot p^{x-1}q^{n-x}
\\
&= np\sum ^{n}_{x=1} {}_{n-1}\mathrm{C}_{x-1}p^{x-1}q^{n-x}
\\
&= np\sum ^{n}_{x=1} {}_{n-1}\mathrm{C}_{x-1}p^{x-1}q^{ {\color{red}n-x-1+1}}
\\
&= np\sum ^{n}_{x=1} {}_{n-1}\mathrm{C}_{x-1}p^{x-1}q^{ {\color{red}n-1-(x-1)}}
\end{aligned}$$

ここで、 $y=x-1, m=n-1$ とおくと

$$\begin{aligned}
&= np\sum ^{ {\color{red}n-1}}_{ {\color{red}y=0}} {}_{n-1}\mathrm{C}_{ {\color{red}y}}p^{ {\color{red}y}}q^{n-1-{\color{red}y}}
\\
&= np\sum ^{ {\color{red}m}}_{y=0} {}_{\color{red}m}\mathrm{C}_y p^{y}q^{ {\color{red}m}-y}
\\
&= np\sum ^{m}_{y=0} {}_m\mathrm{C}_y p^{y}q^{m-y}
\\
&= np \cdot 1
\\
&= np
\end{aligned}$$


### $(2)$ の証明

分散の定義より

$$\begin{aligned}
V(X) &= \sum^{N}_{i=1}(x_i - \mu)^2 f(x_i)
\\
&= \sum^{N}_{i=1}({x_i}^2 - 2{x_i}\mu + \mu^2)f(x_i)
\\
&= \sum^{N}_{i=1}{x_i}^2 f(x_i) - \sum^{N}_{i=1}2{x_i}\mu f(x_i) + \sum^{N}_{i=1}\mu^2 f(x_i)
\\
&= \sum^{N}_{i=1}{x_i}^2 f(x_i) - 2\mu\sum^{N}_{i=1}{x_i} f(x_i) + \mu^2\sum^{N}_{i=1}f(x_i)
\\
&= E(X^2) - 2\mu E(X) + \mu^2 \cdot 1
\\
&= E(X^2) - 2[E(X)]^2 + [E(X)]^2
\\
&= E(X^2) + (- 2 + 1)[E(X)]^2
\\
&= E(X^2) - [E(X)]^2
\end{aligned}$$

と変形できる。いま

$$\begin{aligned}
E\left( X^2\right) &= \sum ^{n}_{x=0}x^2{}_{n}\mathrm{C}_{x}p^{x}q^{n-x}
\\
&= 0^2{}_n\mathrm{C}_0 p^{0}q^{n-0} + \sum ^{n}_{ {\color{red}x=1}}x^2{}_{n}\mathrm{C}_{x}p^{x}q^{n-x}
\\
&= {\color{red}0} + \sum ^{n}_{x=1}x^2\cdot{}_{n}\mathrm{C}_{x}p^{x}q^{n-x}
\\
&= \sum ^{n}_{x=1} {\color{red} (x^2 - x + x) } \cdot {}_{n}\mathrm{C}_{x}p^{x}q^{n-x}
\\
&= \sum ^{n}_{x=1} (x^2 - x) \cdot {}_{n}\mathrm{C}_{x}p^{x}q^{n-x} + \sum ^{n}_{x=1} x \cdot {}_{n}\mathrm{C}_{x}p^{x}q^{n-x}
\\
&= \sum ^{n}_{x=1} (x^2 - x) \cdot {}_{n}\mathrm{C}_{x}p^{x}q^{n-x} + np
\\
&= \sum ^{n}_{x=1} x(x-1) \cdot {}_{n}\mathrm{C}_{x} \cdot {\color{red}p} \cdot {\color{red}p} \cdot p^{x-2}q^{n-x} + np
\\
&= p^2 \sum ^{n}_{x=1} x(x-1) \frac{n!}{(n-x)!x!} p^{x-2}q^{n-x} + np
\\
&= p^2 \sum ^{n}_{x=1} x(x-1) \frac{ {\color{red}n(n-1)(n-2)}!}{(n-x)!{\color{red}x(x-1)(x-2)}!} p^{x-2}q^{n-x} + np
\\
&= n(n-1)p^2 \sum ^{n}_{x=1} \frac{(n-2)!}{(n-x)!(x-2)!} p^{x-2}q^{n-x} + np
\\
&= n(n-1)p^2 \sum ^{n}_{x=1} \frac{(n-2)!}{(n-x-2+2)!(x-2)!} p^{x-2}q^{n-x-2+2} + np
\\
&= n(n-1)p^2 \sum ^{n}_{x=1} \frac{(n-2)!}{[n-2-(x-2)]!(x-2)!} p^{x-2}q^{n-2-(x-2)} + np
\\
&= n(n-1)p^2 \sum ^{n}_{x=1} {}_{n-2}\mathrm{C}_{x-2} p^{x-2}q^{n-2-(x-2)} + np
\\
&= n(n-1)p^2 \sum ^{n}_{x=1} {}_{n-2}\mathrm{C}_{x-2} p^{x-2}q^{n-2-(x-2)} + np
\\
&= n(n-1)p^2 + np
\end{aligned}$$

分散の公式より

$$\begin{aligned}
V(X) &= E(X^2) - [E(X)]^2
\\
&= n(n-1)p^2 + np - (np)^2
\\
&= n^2p^2 - np^2 + np - n^2p^2
\\
&= - np^2 + np
\\
&= np(1-p)
\end{aligned}$$


