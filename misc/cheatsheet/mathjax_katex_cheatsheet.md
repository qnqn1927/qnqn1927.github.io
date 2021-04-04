# mathjax_katex_cheatsheet

- [mathjax_katex_cheatsheet](#mathjax_katex_cheatsheet)
  - [基本演算](#基本演算)
  - [字体](#字体)
  - [装飾](#装飾)
  - [ブロックレベル表記](#ブロックレベル表記)
    - [行列（parentheses）](#行列parentheses)
    - [行列（square brackets）](#行列square-brackets)
    - [行列式](#行列式)


## 基本演算

|内容|記述|出力|
|:-:|:-:|:-:|
|添字|x_i|$x_i$|
|累乗|x^k|$x^k$|
|平方根|\sqrt x|$\sqrt x$|
|立方根|\sqrt[3]x|$\sqrt[3]x$|
|掛け算（ドット積）|x \cdot y|$x \cdot y$|
|割り算|x / y|$x / y$|
|分数|\dfrac{x}{y}|$\dfrac{x}{y}$|


## 字体
|内容|記述|出力|
|:-:|:-:|:-:|
|イタリック体|X|$X$|
|ローマン体|\mathrm{X}|$\mathrm{X}$|


## 装飾
|内容|記述|出力|
|:-:|:-:|:-:|
|赤色|\color{red} X|$\color{red} X$|
|範囲指定で桃色|{\color{pink} a + b} + \sum_{i=1}^n x_i|${\color{pink} a + b} + \sum_{i=1}^n x_i$|



## ブロックレベル表記

### 行列（parentheses）
```
\begin{pmatrix}
a_{11} & a_{12} & a_{13}\\
a_{21} & a_{22} & a_{23}\\
a_{31} & a_{32} & a_{33}\\
\end{pmatrix}
```

$$
\begin{pmatrix}
a_{11} & a_{12} & a_{13}\\
a_{21} & a_{22} & a_{23}\\
a_{31} & a_{32} & a_{33}\\
\end{pmatrix}
$$

### 行列（square brackets）
```
\begin{bmatrix}
a_{11} & a_{12} & a_{13}\\
a_{21} & a_{22} & a_{23}\\
a_{31} & a_{32} & a_{33}\\
\end{bmatrix}
```

$$
\begin{bmatrix}
a_{11} & a_{12} & a_{13}\\
a_{21} & a_{22} & a_{23}\\
a_{31} & a_{32} & a_{33}\\
\end{bmatrix}
$$

### 行列式
```
\begin{vmatrix}
a_{11} & a_{12} & a_{13}\\
a_{21} & a_{22} & a_{23}\\
a_{31} & a_{32} & a_{33}\\
\end{vmatrix}
```

$$
\begin{vmatrix}
a_{11} & a_{12} & a_{13}\\
a_{21} & a_{22} & a_{23}\\
a_{31} & a_{32} & a_{33}\\
\end{vmatrix}
$$
