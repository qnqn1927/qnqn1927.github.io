# チェビシェフの不等式（chebyshev's inequality）

- [チェビシェフの不等式（chebyshev's inequality）](#チェビシェフの不等式chebyshevs-inequality)
  - [概要](#概要)
  - [マルコフの不等式（markov's inequality）](#マルコフの不等式markovs-inequality)
    - [定義](#定義)
    - [証明](#証明)
  - [チェビシェフの不等式（chebyshev's inequality）](#チェビシェフの不等式chebyshevs-inequality)
    - [概要](#概要-1)
    - [証明](#証明-1)
  - [参考文献](#参考文献)

## 概要

下記数式のことを指します。

$$
P\left( |X-\mu| \geq k\sigma\right) \leq \dfrac{1}{k^2}
$$

これは、

どのような分布の確率変数でも、とり得る値の平均からの距離について、 $\sigma$ の $k$ 個分より広がる確率が $\displaystyle\frac{1}{k^2}$ 以下となることを示しています。

例えば $k=2$ のとき $2\sigma$ より離れた値をとる確率は $25\%$ 以下となります。

証明にマルコフの不等式を用いるので、前段として説明したのち、チェビシェフの不等式の証明に移ります。

## マルコフの不等式（markov's inequality）

### 定義

$X$ が非負の確率変数かつ $a>0$ のとき、下記の不等式が成立することをいいます。

$$
P\left( X\geq a\right) \leq \dfrac{E\left( X\right) }{a}
$$

これは $X$ が $a$ 以上をとる確率は最も高くて $E(X)$ を $a$ で割った値となることを示しています。

### 証明

$X$ を負の値をとらない確率変数とします。 $a$ は任意の正の値とします。

$$\begin{aligned}
E\left( X\right) =\int _{-\infty }^{\infty }xf\left( x\right) dx
\end{aligned}$$

$X$ が負の値をとらないことにより

$$\begin{aligned}
&= \int _{0}^{\infty }xf\left( x\right) dx
\\
&\geq \int _{a}^{\infty }xf\left( x\right) dx &&\text{(a>0のため)}
\end{aligned}$$

すべての $x$ を $a$ に置き換える。このとき $x>a$ は成り立っています。

$$\begin{aligned}
&\geq \int ^{\infty }_{a}af\left( x\right) dx
\\
&= a\int _{a}^{\infty }f\left( x\right) dx
\\
&= aP\left( X\geq a\right) 
\\
P\left( X\geq a\right) &\leq \dfrac{E\left( x\right) }{a}
\end{aligned}$$


## チェビシェフの不等式（chebyshev's inequality）

### 概要

確率分布が未知で任意の値をとり得る確率変数 $X$ において $E(X)=\mu,Var(X)=\sigma^2$ であり、下記が成立します。

$$
P\left( |X-\mu| \leq k\sigma\right) \geq 1 - \dfrac{1}{k^2}
$$

### 証明

$X$ を任意の値をとる確率変数とおくと
$$E(X)=\mu,Var(X)=\sigma^2$$
です。

また、 $(X-\mu)^2$ は非負の値をとる確率変数であり、マルコフの不等式を適用することができます。

$$\begin{aligned}
P\left( X\geq a\right) &\leq \dfrac{E\left( X\right) }{a} &&(\text{マルコフの不等式})
\\
P\left[ (X-\mu)^2 \geq a\right] &\leq \dfrac{E\left[ (X-\mu)^2\right] }{a} &&(\text{マルコフの不等式より})
\\
P\left[ (X-\mu)^2 \geq a\right] &\leq \dfrac{ \sigma^2 }{a} &&(E\left[ (X-\mu)^2\right]=\sigma^2)
\\
P\left[ (X-\mu)^2 \geq k^2\sigma^2\right] &\leq \dfrac{ \sigma^2 }{k^2\sigma^2} &&(a=k^2\sigma^2\text{とおく})
\\
P\left( |X-\mu| \geq k\sigma\right) &\leq \dfrac{1}{k^2}
\end{aligned}$$

が成り立ちます。余事象を考えると

$$
P\left( |X-\mu| \leq k\sigma\right) \geq 1 - \dfrac{1}{k^2}
$$

となります。

## 参考文献
- 東京大学教養学部統計学教室『統計学入門 (基礎統計学Ⅰ) (日本語) 単行本 – 1991/7/9』
- 西内 啓『統計学が最強の学問である［実践編］』
