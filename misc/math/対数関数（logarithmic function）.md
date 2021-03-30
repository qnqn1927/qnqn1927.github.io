# 対数関数（logarithmic function）

- [対数関数（logarithmic function）](#対数関数logarithmic-function)
  - [計算ルール](#計算ルール)
    - [両辺に対数を取っても良い](#両辺に対数を取っても良い)
    - [対数の掛け算は足し算に変形できる](#対数の掛け算は足し算に変形できる)
    - [対数の割り算は引き算に変形できる](#対数の割り算は引き算に変形できる)
    - [対数の肩にある指数は前に降ろすことができる](#対数の肩にある指数は前に降ろすことができる)
  - [計算ルールの証明](#計算ルールの証明)
    - [(2)対数の掛け算は足し算に変形できる](#2対数の掛け算は足し算に変形できる)
    - [(3)対数の割り算は引き算に変形できる](#3対数の割り算は引き算に変形できる)
    - [(4)対数の肩にある指数は前に降ろすことができる](#4対数の肩にある指数は前に降ろすことができる)
  - [参考文献](#参考文献)

## 計算ルール

成立条件として、底は1以外のプラスの実数である必要があります。

### 両辺に対数を取っても良い


$$x = y \Leftrightarrow \log_ax = \log_ay \tag{1}$$


両辺に同じ底の対数をとっても同値であることが保証されています。

グラフで考えるとイメージしやすいです。単調増加、単調減少が理解を助けてくれます。


### 対数の掛け算は足し算に変形できる


$$\log_axy = \log_ax + \log_ay \tag{2}$$


### 対数の割り算は引き算に変形できる


$$\log_a\dfrac{x}{y} = \log_ax - \log_ay \tag{3}$$


### 対数の肩にある指数は前に降ろすことができる


$$\log_ax^y = y \log_ax \tag{4}$$


## 計算ルールの証明

### (2)対数の掛け算は足し算に変形できる


$$\begin{aligned}
&&xy &= a^{\log_a x}a^{\log_a y}\\
\Leftrightarrow&& xy &= a^{\log_a x + \log_a y} \quad~\cdots(指数法則)\\
\Leftrightarrow&& \log_a xy &= \log_a a^{\log_a x + \log_a y}\\
\Leftrightarrow&& \log_a xy &= \log_a x + \log_a y
\end{aligned}$$


### (3)対数の割り算は引き算に変形できる


$$\begin{aligned}
&& \dfrac{x}{y}
&= \dfrac{a^{\log_a x}}{a^{\log_a y}}\\

\Leftrightarrow&& \dfrac{x}{y}
&= a^{\log_a x} a^{(-\log_a y)}\\

\Leftrightarrow&& \dfrac{x}{y}
&= a^{\log_a x - \log_a y} \quad~\cdots(指数法則)\\

\Leftrightarrow&& \log_a \dfrac{x}{y}
&= \log_a a^{\log_a x - \log_a y}\\

\Leftrightarrow&& \log_a \dfrac{x}{y}
&= \log_a x - \log_a y
\end{aligned}$$


### (4)対数の肩にある指数は前に降ろすことができる


$$\begin{aligned}
&& x^y &= a^{\log_a x^y}\\

\Leftrightarrow&& x^y &= (a^{\log_a x})^y\\

\Leftrightarrow&& x^y &= a^{y \cdot \log_a x} \quad~\cdots(指数法則)\\

\Leftrightarrow&& \log_a x^y
&= \log_a a^{y \cdot \log_a x}\\

\Leftrightarrow&& \log_ax^y &= y \log_ax\\

\end{aligned}$$


## 参考文献
- 西内 啓『統計学が最強の学問である[数学編]――データ分析と機械学習のための新しい教科書』

