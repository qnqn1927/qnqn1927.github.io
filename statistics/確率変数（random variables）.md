# 確率変数（random variables）

- [確率変数（random variables）](#確率変数random-variables)
  - [確率変数の定義](#確率変数の定義)
    - [確率変数は2夕イプあります！](#確率変数は2夕イプあります)
      - [離散型（discrete type）](#離散型discrete-type)
      - [連続型（continuous type）](#連続型continuous-type)
  - [同時確率分布の定義](#同時確率分布の定義)
  - [周辺確率分布の定義](#周辺確率分布の定義)
  - [平均・分散の性質](#平均分散の性質)
    - [平均の性質](#平均の性質)
    - [分散の性質](#分散の性質)
    - [proof $(1.1)$](#proof-11)
    - [proof $(1.2)$](#proof-12)
    - [proof $(1.4)$](#proof-14)
    - [proof $(2.3)$](#proof-23)
  - [参考文献](#参考文献)


## 確率変数の定義

確率変数（random variable）

→ 取り得る値それぞれに対して確率が与えられている変数のこと

大文字を使って表します。

e.g. $X,Y$

確率は $P(X=x)$ で表します。

1〜6が出るサイコロで考えると、

$$
P\left( X=1\right) =\dfrac{1}{6},P\left( X=2\right) =\dfrac{1}{6},\ldots ,P\left( X=6\right) =\dfrac{1}{6}
$$

となります。

### 確率変数は2夕イプあります！

| 名称 | 英語名称 | 定義 |
|:-:|:-:|:-:|
| 離散型 | discrete type | サイコロの目など取り得る値が「1, 2, 3」ととびとびの値をとるものを指す |
| 連続型 | continuous type | 長さ、重さなど取り得る値が「1.1, 1.10」といったように区切りがないものを指す |

タイプにより表し方が異なります。

#### 離散型（discrete type）

$$
P\left( X=x_{i}\right) =f\left( x_{i}\right)
$$

成立条件は下記です。

$$
\begin{aligned}
f\left( x_{i}\right) \geq 0\\
\sum ^{\infty }_{i=1}f\left( x_{i}\right) =1 & \cdots (全部足し合わせると1)
\end{aligned}
$$

#### 連続型（continuous type）

$$
\begin{aligned}
P\left( a\leq X\leq b\right) =\int _{a}^{b}f\left( x\right) dx\\
\end{aligned}
$$

成立条件は下記です。

$$
\begin{aligned}
f\left( x\right) \geq 0\\
\int ^{\infty }_{-\infty }f\left( x\right) dx=1 & \cdots (全部足し合わせると1)
\end{aligned}
$$

## 同時確率分布の定義

確率変数 $X$, $Y$ において、同時に $X=x$ かつ $Y=y$ の値をとる確率 $P$ を

$$P(X=x,Y=y)=f(x,y)$$

として、これを同時確率分布といいます。


## 周辺確率分布の定義

$X,Y$ の確率変数において、一方の値を固定した時に得られる $X,Y$ 単独の確率分布を周辺確率分布といいます。

$$\begin{aligned}
g(x) = \sum_{i=1}^{N_Y}f(x,y_i)
\\
h(y) = \sum_{i=1}^{N_X}f(x_i,y)
\end{aligned}$$



e.g.

表裏のある2枚のコインA, Bを用意します。

表は $1$、裏は $0$ とします。

コインAは
$$X={0,1}$$
とおきます。

コインBはコインAの結果の値を足したものとします。

したがって、コインBは
$$Y={0,1,2}$$
となります。

このときの同時確率分布は下表となります。

| $Y \backslash X$ | $x_1$ | $x_2$ | $h(y)$ |
|:-:|:-:|:-:|:-:|
| $y_1$ | $\frac{1}{4}$ | $0$ | $\frac{1}{4}$ |
| $y_2$ | $\frac{1}{4}$ | $\frac{1}{4}$ | $\frac{2}{4}$ |
| $y_3$ | $0$ | $\frac{1}{4}$ | $\frac{2}{4}$ |
| $g(x)$ | $\frac{2}{4}$ | $\frac{2}{4}$ | $1$ |

ここで $g(x),h(y)$ が周辺確率分布を示しています。


## 平均・分散の性質

### 平均の性質

$$
\begin{aligned}
E(c) &= c &\quad\quad&\llap{(1.1)}\\
E(X + c) &= E(X) + c &&\llap{(1.2)}\\
E(cX) &= cE(X) &&\llap{(1.3)}\\
E(X + Y) &= E(X) + E(Y) &&\llap{(1.4)}
\end{aligned}
$$

### 分散の性質

$$
\begin{aligned}
V(c) &= 0 &\quad\quad&\llap{(2.1)}\\
V(X + c) &= V(X) &&\llap{(2.2)}\\
V(cX) &= c^{2}V(X) &&\llap{(2.3)}
\end{aligned}
$$

### proof $(1.1)$

定数はばらつきのない値なので、期待値はそのままとなります。

### proof $(1.2)$


$$
\begin{aligned}
E\left( X+c\right) &= \sum ^{n}_{i=1}\dfrac{\left( X_{i}+c\right) }{n}\\
&= \dfrac{1}{n}\sum ^{n}_{i=1}\left( X_{i}+c\right) \\
&= \dfrac{1}{n}\left\{ \left( X_{1}+c\right) +\left( X_{2}+c\right) +\ldots +\left( X_{n}+c\right) \right\} \\
&= \dfrac{1}{n}\left( X_{1}+X_{2}+\ldots +X_{n}+nc\right) \\
&= \dfrac{X_{1}+X_{2}+\ldots +X_{n}}{n}+c\\
&= E\left( X\right) +c
\end{aligned}
$$



### proof $(1.4)$


$$
\begin{aligned}
E\left( X+Y\right) &= \sum ^{N_X}_{i=1}\sum ^{N_Y}_{j=1}\left( x_{i}+y_{i}\right) f\left( x_{i},y_{j}\right)\\
&= \sum ^{N_X}_{i=1}\left\{ \sum ^{N_Y}_{j=1} x_{i} f \left( x_{i},y_{j}\right) + \sum ^{N_Y}_{j=1}y_{i} f \left( x_{i},y_{j} \right) \right\} \\
&= \sum ^{N_X}_{i=1}\left\{ x_{i} \sum ^{N_Y}_{j=1} f \left( x_{i},y_{j}\right) + \sum ^{N_Y}_{j=1}y_{i} f \left( x_{i},y_{j} \right) \right\} \\
&= \sum ^{N_X}_{i=1} x_{i} \sum ^{N_Y}_{j=1} f \left( x_{i},y_{j}\right) + \sum ^{N_X}_{i=1} \sum ^{N_Y}_{j=1} y_{i} f \left( x_{i},y_{j} \right) \\
&= \sum ^{N_X}_{i=1} x_{i} \sum ^{N_Y}_{j=1} f \left( x_{i},y_{j}\right) + \sum ^{N_Y}_{j=1}\sum ^{N_X}_{i=1} y_{i} f \left( x_{i},y_{j} \right) \\
&= \sum ^{N_X}_{i=1} x_{i} \sum ^{N_Y}_{j=1} f \left( x_{i},y_{j}\right) + \sum ^{N_Y}_{j=1} y_{i} \sum ^{N_X}_{i=1} f \left( x_{i},y_{j} \right) \\
\end{aligned}
$$

周辺確率分布より

$$
\begin{aligned}
&= \sum ^{N_X}_{i=1} x_{i}g(x_i) + \sum ^{N_Y}_{j=1} y_{i}h(y_i) \\
&= E(X) + E(Y)
\end{aligned}
$$



### proof $(2.3)$



$E(X) = \mu$ とすると $E(cX) = cE(X) = c\mu$ となる。そして

$$\begin{aligned}
Var(cX)
&= E \left[ (cX - c\mu)^2 \right]
\\
&= E \left\{ \left[c (X - \mu) \right]^2 \right\}
\\
&= E \left[ c^2 (X - \mu)^2 \right]
\\
&= c^2 E \left[ (X - \mu)^2 \right]
\\
&= c^2 E \left[ (X - \mu)^2 \right]
\\
&= c^{2}V(X)
\end{aligned}$$



## 参考文献

- 東京大学教養学部統計学教室『統計学入門 (基礎統計学Ⅰ) (日本語) 単行本 – 1991/7/9』


