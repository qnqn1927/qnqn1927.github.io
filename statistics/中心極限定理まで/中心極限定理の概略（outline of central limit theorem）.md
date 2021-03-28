# 中心極限定理の概略（outline of central limit theorem）

- [中心極限定理の概略（outline of central limit theorem）](#中心極限定理の概略outline-of-central-limit-theorem)
  - [中心極限定理を簡略化して説明](#中心極限定理を簡略化して説明)
  - [標本平均の平均と分散](#標本平均の平均と分散)
    - [$\bar{X}$の平均は？](#barxの平均は)
    - [$\bar{X}$の分散は？](#barxの分散は)
  - [正規分布の再生性](#正規分布の再生性)
  - [参考文献](#参考文献)

## 中心極限定理を簡略化して説明

$n$個の確率変数があります：$X_1,X_2,...,X_n$

それらの条件は

- 互いに独立
- 同一の分布に従う。ただしどんな分布でも良い
- 平均$\mu$、分散$\sigma^2$

このとき、$n$が大きくなるとそれらの『平均』もしくは『総和』は

$$
\bar{X} = \dfrac{1}{n}\sum_{i=1}^{n}X_i \sim N(\mu, \sigma^2/n)
$$

$$
Xの総和 = \sum_{i=1}^{n}X_i \sim N(n\mu, n\sigma^2)
$$

と考えてよい、という法則です。

独立な確率変数の

- 『足し合わせて平均をとったもの』
- 『足し合わせた総和』

これらは、「サンプルサイズが十分に大きければ」正規分布に近似するとみなしてよいというところが要点です。

「元の分布が正規分布に従うと述べているわけではない」ことに留意する必要があります。近似するのは『平均』か『総和』です。


## 標本平均の平均と分散

以下の公式を用いて示します。

$$\begin{aligned}
& E(X+Y) = E(X) + E(Y)\\
& V(X+Y) = V(X) + V(Y) + 2C(X,Y)\\
& （独立であるなら）V(X+Y) = V(X) + V(Y)
\end{aligned}$$

### $\bar{X}$の平均は？

$$\begin{aligned}
E(\bar{X}) &= E\left(
    \dfrac{1}{n}\sum_{i=1}^{n}X_i
    \right)\\
&= \dfrac{1}{n} E\left(
    \sum_{i=1}^{n}X_i
    \right)\\
&= \dfrac{1}{n} E\left(
    X_1 + X_2 + ... + X_n
    \right)\\
\end{aligned}$$

公式を繰り返し適用することにより

$$\begin{aligned}
& \dfrac{1}{n} \left[
    E(X_1) + E(X_2) + ... + E(X_n)
    \right]
\end{aligned}$$

独立同一分布より$E(X_i)=E(X)$となるので

$$\begin{aligned}
&\quad~ \dfrac{1}{n} \left[
    E(X) + E(X) + ... + E(X)
    \right]\\
&= \dfrac{1}{n} nE(X)\\
&= E(X)\\
&= \mu
\end{aligned}$$

$\bar{X}$の期待値は$\mu$であることがわかりました。

### $\bar{X}$の分散は？

$$\begin{aligned}
V(\bar{X}) &= V\left(
    \dfrac{1}{n}\sum_{i=1}^{n}X_i
    \right)\\
&= \dfrac{1}{n^2} V\left(
    \sum_{i=1}^{n}X_i
    \right)\\
&= \dfrac{1}{n^2} V\left(
    X_1 + X_2 + ... + X_n
    \right)\\
\end{aligned}$$

公式を繰り返し適用することにより

$$\begin{aligned}
& \dfrac{1}{n^2} \left[
    V(X_1) + V(X_2) + ... + V(X_n)
    \right]
\end{aligned}$$

独立同一分布より$V(X_i)=V(X)$となるので

$$\begin{aligned}
&\quad~ \dfrac{1}{n^2} \left[
    V(X) + V(X) + ... + V(X)
    \right]\\
&= \dfrac{1}{n^2} nV(X)\\
&= \dfrac{V(X)}{n}\\
&= \dfrac{\sigma^2}{n}
\end{aligned}$$

$\bar{X}$の分散は$\dfrac{\sigma^2}{n}$であることがわかりました。

したがって、下記の平均と分散が示されたことになります。

$$
\bar{X} = \dfrac{1}{n}\sum_{i=1}^{n}X_i \sim N(\mu, \sigma^2/n)
$$

Xの総和は

$$E(Xの総和) = E\left( \sum_{i=1}^{n}X_i \right)$$

であり $\bar{X}$ の場合から $\dfrac{1}{n}$ が消えたかたちのものだとわかります。

$$cf.~ E(\bar{X}) = E\left( \dfrac{1}{n}\sum_{i=1}^{n}X_i \right)$$

したがって、$\bar{X}$ の場合と見比べますと、期待値から $\dfrac{1}{n}$ 、分散から $\dfrac{1}{n^2}$ が消えたものだとわかります。

$\bar{X}$ のときと同様の計算を行うことで期待値 $n\mu$ 、分散 $n\sigma^2$ が得られ、

$$Xの総和 = \sum_{i=1}^{n}X_i \sim N(n\mu, n\sigma^2)$$

が示されました。

## 正規分布の再生性

独立に正規分布に従う2つの確率変数があるとき

$$\begin{aligned}
& X + Y \sim N(\mu_1 + \mu_2, \sigma_1^2 + \sigma_2^2)
\end{aligned}$$

（執筆中）



## 参考文献
- 倉田 博史(著), 星野 崇宏(著)『入門統計解析』
