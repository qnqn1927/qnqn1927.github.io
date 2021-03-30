# 微分について（differential）

- [微分について（differential）](#微分についてdifferential)
  - [微分の定義](#微分の定義)
  - [微分をツールとして機械的に用いる場合は公式を活用する](#微分をツールとして機械的に用いる場合は公式を活用する)
    - [$n$ 次関数の微分](#n-次関数の微分)
      - [証明](#証明)
        - [$n$ が自然数の場合の証明](#n-が自然数の場合の証明)
    - [合成関数の微分](#合成関数の微分)
      - [考え方](#考え方)
      - [（例題）](#例題)
    - [積の微分・商の微分](#積の微分商の微分)
      - [積の微分の考え方](#積の微分の考え方)
      - [商の微分の考え方](#商の微分の考え方)
  - [多変数における微分](#多変数における微分)
    - [偏微分](#偏微分)
  - [参考文献](#参考文献)

## 微分の定義
微分とはごく微かにxが変化した際のyの変化量を調べるものである


$$
\dfrac{dy}{dx}=\dfrac{d}{dx}f\left( x\right) =\lim _{\Delta x\rightarrow 0}\dfrac{\Delta y}{\Delta x}=\lim _{\Delta x\rightarrow 0 }\dfrac{f\left( x+\Delta x\right) -f\left( x\right) }{\Delta x}
$$


## 微分をツールとして機械的に用いる場合は公式を活用する

### $n$ 次関数の微分

$$
\dfrac{d}{dx}x^{n} = nx^{\left( n-1\right) }
$$


#### 証明

##### $n$ が自然数の場合の証明


$$
\begin{aligned}
\dfrac{d}{dx}x^{n}&=\lim _{\Delta x\rightarrow 0}\dfrac{f\left( x+\Delta x\right) -f\left( x\right) }{\Delta x}
\\
&=\lim _{\Delta x\rightarrow 0}\dfrac{\left( x+\Delta x\right) ^{n}-x^{n}}{\Delta x}
\\
&=\lim _{\Delta x\rightarrow 0}\dfrac{\sum ^{n}_{k=0}\left( {}_n\mathrm{C}_{k}x^{n-k}\Delta x^{k}\right) -x^{n}}{\Delta x}
\\
&=\lim _{\Delta x\rightarrow 0}\dfrac{ {}_n\mathrm{C}_{0}x^{n}\Delta x^{0}+{}_n\mathrm{C}_{1}x^{n-1}\Delta x^{1}+{}_n\mathrm{C}_{2}x^{n-2}\Delta x^{2}+\ldots +{}_n\mathrm{C}_{n}x^{0}\Delta x^{n}-x^{n}}{\Delta x}
\\
&=\lim _{\Delta x\rightarrow 0}\dfrac{x^{n}+nx^{n-1}\Delta x+ {}_n\mathrm{C}_{2}x^{n-2}\Delta x^{2}+\ldots +\Delta x^{n}-x^{n}}{\Delta x}
\\
&=\lim _{\Delta x\rightarrow 0}\dfrac{nx^{n-1}\Delta x+{}_n\mathrm{C}_{2}x^{n-2}\Delta x^{2}+\ldots +\Delta x^{n}}{\Delta x}
\\
&=\lim _{\Delta x\rightarrow 0}nx^{n-1}+{}_n\mathrm{C}_{2}x^{n-2}\Delta x^{2-1}+\ldots +\Delta x^{n-1}
\\
\end{aligned}
$$

$\Delta x$ が乗算されている項は極限を考えると $0$ になることより

$$
\begin{aligned}
&=nx^{n-1}
\end{aligned}
$$


### 合成関数の微分

#### 考え方

外の微分、中の微分と覚えると良い。

$y=f\{g(x)\}$ において $g(x)=u$ とおくと、$\dfrac{dy}{dx}$ は $\dfrac{dy}{du}\dfrac{du}{dx}$ と考えることができる。

#### （例題）


次式を微分する。

$$
y=(x^2+x+1)^3
$$

$u=x^2+x+1$ とおくと外は「 $u^3$ 」、中は「 $x^2+x+1$ 」となる。

$$\begin{aligned}
\dfrac{dy}{dx} &= \dfrac{dy}{du}\dfrac{du}{dx}
\\
&= 3u^2(2x+1)
\\
&= 3(x^2+x+1)^2(2x+1)
\end{aligned}$$


### 積の微分・商の微分

積の微分は $f(x)g(x)$ 、商の微分は $\dfrac{f(x)}{g(x)}$ と表す。

#### 積の微分の考え方


$$
h(x) = f(x)g(x)
$$

とすると微分の定義より、

$$\begin{aligned}
\dfrac{d}{dx}h(x) &= \lim _{\Delta x\rightarrow 0}\dfrac{ f(x+\Delta{x})g(x+\Delta{x})-f(x)g(x) }{ \Delta{x} }
\\
&= \lim _{\Delta x\rightarrow 0}\dfrac{ f(x+\Delta{x})g(x+\Delta{x}) {\color{red} -f(x)g(x+\Delta{x})+f(x)g(x+\Delta{x})} -f(x)g(x) }{ \Delta{x} }&&(同じ値を引いて足している)
\end{aligned}$$

ここで $f(x)$ および $g(x)$ の微分の定義を考えると、

$$\begin{aligned}
\dfrac{d}{dx}f(x) &= \lim _{\Delta x\rightarrow 0}\dfrac{ f(x + \Delta{x}) - f(x) }{ \Delta{x} }
\\
\dfrac{d}{dx}g(x) &= \lim _{\Delta x\rightarrow 0}\dfrac{ g(x + \Delta{x}) - g(x) }{ \Delta{x} }
\end{aligned}$$

これにより、

$$\begin{aligned}
&\quad \lim _{\Delta x\rightarrow 0}\dfrac{
    f(x+\Delta{x}) {\color{red} g(x+\Delta{x})} -f(x) {\color{red} g(x+\Delta{x}) } + {\color{green} f(x)} g(x+\Delta{x}) - {\color{green} f(x)} g(x)
}{
    \Delta{x}
}
\\
&= \lim _{\Delta x\rightarrow 0}\dfrac{
    {\color{red} g(x + \Delta{x}) } \left[ f(x+\Delta{x}) - f(x) \right]
    +
    {\color{green} f(x) } \left[ g(x+\Delta{x}) - g(x) \right]
}{
    \Delta{x}
}
\\
&= \lim _{\Delta x\rightarrow 0} \left[
g(x + \Delta{x})
\dfrac{
    f(x+\Delta{x}) - f(x)
}{
    \Delta{x}
}
+
f(x)
\dfrac{
    g(x+\Delta{x}) - g(x)
}{
    \Delta{x}
}
\right]
\\
&= g(x)\dfrac{d}{dx}f(x)
+
f(x)\dfrac{d}{dx}g(x)

\end{aligned}$$


#### 商の微分の考え方


$\dfrac{f(x)}{g(x)}$ は $f(x)[g(x)^{-1}]$ と表すことができ、積の微分として考えることができる。

$$\begin{aligned}
\dfrac{d}{dx}\left\{ f(x) \left[ g(x) \right]^{-1} \right\}
&=
f'(x) \left[ g(x)\right]^{-1} 
+ f(x) \left[ g(x)^{-1} \right]'
\\
&= f'(x)g(x)^{-1} + f(x) -1 \cdot \left[g(x)\right]^{-2} \cdot g'(x)
\\
&= \dfrac{ f'(x) }{ g(x) }
-
\dfrac{ f(x)g'(x) }{ \left[ g(x) \right]^2 }
\\
&= \dfrac{ f'(x)g(x) }{ g(x)g(x) }
-
\dfrac{ f(x)g'(x) }{ \left[ g(x) \right]^2 }
\\
&= \dfrac{ f'(x)g(x) - f(x)g'(x) }{ \left[ g(x) \right]^2 }
\end{aligned}$$


## 多変数における微分

### 偏微分

$\partial$ という記号を用いて表す。これはパーシャルと読む。

$\dfrac{\partial{y}}{\partial{x}}$ は $y$ を $x$ で偏微分するということを示している。






## 参考文献
- 西内 啓  (著)『統計学が最強の学問である[数学編]――データ分析と機械学習のための新しい教科書』 
