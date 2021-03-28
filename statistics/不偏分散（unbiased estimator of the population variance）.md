# 不偏分散（unbiased estimator of the population variance）

- [不偏分散（unbiased estimator of the population variance）](#不偏分散unbiased-estimator-of-the-population-variance)
  - [なぜ $n-1$ で割り算するのか](#なぜ-n-1-で割り算するのか)
  - [数式で確認](#数式で確認)

## なぜ $n-1$ で割り算するのか

標本分散 $S^2$ の期待値をとってみると

$$\dfrac{n-1}{n}\sigma^2$$

となります。

これは、母分散を $\dfrac{1}{n}$ だけ過小評価していることがわかります。

この過小評価を打ち消すために、不偏分散 $s^2$ は $n-1$ で割り算しています。

## 数式で確認

標本分散は

$$
S^2 = \dfrac{1}{n}\sum^{n}_{i=1}(X_i - \bar{X})^2
$$

です。

準備のため次の演算をします。

$$\begin{aligned}
\dfrac{1}{n}\sum^{n}_{i=1}(X_i - \bar{X})^2
&= \dfrac{1}{n}\sum^{n}_{i=1}(X_i {\color{red} - \mu + \mu } - \bar{X})^2
\\
&= \dfrac{1}{n}\sum^{n}_{i=1} \left[(X_i - \mu) - (\bar{X} - \mu) \right]^2
\\
&= \dfrac{1}{n}\sum^{n}_{i=1} \left[ (X_i - \mu)^2
- 2(X_i - \mu)(\bar{X} - \mu )
+ (\bar{X} - \mu )^2 \right]
\\
&= \dfrac{1}{n}\sum^{n}_{i=1} (X_i - \mu)^2
- \dfrac{1}{n}\sum^{n}_{i=1} \left[ 2(X_i - \mu)(\bar{X} - \mu ) \right]
+ \dfrac{1}{n}\sum^{n}_{i=1} (\bar{X} - \mu )^2
\\
&= \dfrac{1}{n}\sum^{n}_{i=1} (X_i - \mu)^2
{\color{red}
- \dfrac{2(\bar{X} - \mu)}{n} \sum^{n}_{i=1} (X_i - \mu)
+ (\bar{X} - \mu)^2
}
\\
&= \dfrac{1}{n}\sum^{n}_{i=1} (X_i - \mu)^2
- \dfrac{2(\bar{X} - \mu)}{n} {\color{red} \left[ (X_1 + X_2 + \cdots + X_n) - n\mu \right]}
+ (\bar{X} - \mu)^2
\\
&= \dfrac{1}{n}\sum^{n}_{i=1} (X_i - \mu)^2
- \dfrac{2(\bar{X} - \mu)}{n} \left( n\bar{X} - n\mu \right)
+ (\bar{X} - \mu)^2
\\
&= \dfrac{1}{n}\sum^{n}_{i=1} (X_i - \mu)^2
- 2(\bar{X} - \mu) (\bar{X} - \mu)
+ (\bar{X} - \mu)^2
\\
&= \dfrac{1}{n}\sum^{n}_{i=1} (X_i - \mu)^2
- 2(\bar{X} - \mu)^2
+ (\bar{X} - \mu)^2
\\
&= \dfrac{1}{n}\sum^{n}_{i=1} (X_i - \mu)^2
- (\bar{X} - \mu)^2
\end{aligned}$$

また

$$\begin{aligned}
Var(X) &= \dfrac{1}{n} \sum^{n}_{i=1} (X_i - \mu)^2
\\
&= \sigma^2
\\
Var(\bar{X}) &= Var\left( \dfrac{1}{n} \sum^{n}_{i=1} X_i \right)
\\
&= \dfrac{1}{n^2} \sum^{n}_{i=1} Var\left( X_i \right)
\\
&= \dfrac{1}{n^2} \left[ Var\left( X_1 \right) + Var\left( X_2 \right) + \cdots + Var\left( X_n \right) \right]
\\
&= \dfrac{1}{n^2}n\sigma^2 = \dfrac{\sigma^2}{n}
\end{aligned}$$

です。

これで準備が整いました。

いま、標本分散の期待値を考えますと、

$$\begin{aligned}
E(S^2) &= E \left[ \dfrac{1}{n}\sum^{n}_{i=1} (X_i - \mu)^2 - (\bar{X} - \mu)^2 \right]
\\
&= E \left[ \dfrac{1}{n}\sum^{n}_{i=1} (X_i - \mu)^2 \right]
- E \left[ (\bar{X} - \mu)^2 \right]
\\
&= \dfrac{1}{n}\sum^{n}_{i=1} E \left[ (X_i - \mu)^2 \right]
- Var(\bar{X})
\\
&= \dfrac{1}{n}\sum^{n}_{i=1} Var(X_i)
- Var(\bar{X})
\\
&= \sigma^2 - \dfrac{\sigma^2}{n}
\\
&= \dfrac{n-1}{n}\sigma^2
\end{aligned}$$

ここで、$\dfrac{1}{n}$ 過小評価されていることが分かります。

式のかたちを変えてみますと、

$$\begin{aligned}
& E(S^2)
\\
=~& \dfrac{1}{n}\sum^{n}_{i=1}(X_i - \bar{X})^2
= \dfrac{n-1}{n}\sigma^2
\\
\Leftrightarrow~& \dfrac{n}{n-1} \cdot \dfrac{1}{n}\sum^{n}_{i=1}(X_i - \bar{X})^2
= \dfrac{n}{n-1} \cdot \dfrac{n-1}{n}\sigma^2
\\
\Leftrightarrow~& \dfrac{1}{n-1} \sum^{n}_{i=1}(X_i - \bar{X})^2
= \sigma^2
\end{aligned}$$

よって、不偏分散は $n-1$ で除算することにより、母分散を推定できることが示されました。

$$
s^2 = \dfrac{1}{n-1} \sum^{n}_{i=1}(X_i - \bar{X})^2
= \sigma^2
$$



