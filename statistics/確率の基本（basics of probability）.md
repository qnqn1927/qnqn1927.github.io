# 確率の基本（basics of probability）

- [確率の基本（basics of probability）](#確率の基本basics-of-probability)
  - [用語まとめ](#用語まとめ)
  - [標本空間と事象について](#標本空間と事象について)
  - [事象に関する法則および性質](#事象に関する法則および性質)
    - [和事象・積事象の分配法則](#和事象積事象の分配法則)
    - [ド・モルガンの法則](#ドモルガンの法則)
    - [加法定理](#加法定理)
    - [条件付き確率](#条件付き確率)
      - [乗法定理](#乗法定理)
    - [独立性](#独立性)
  - [参考文献](#参考文献)

## 用語まとめ

| 名称 | 英語名称 | 数学記号 | 説明 |
|:-:|:-:|:-:|:-:|
| 起こりうる結果 | possible outcomes |  | ある試行においてとりうることが可能な値 |
| 標本点| sample point | $\omega$ | 起こりうる結果のひとつひとつのこと |
| 標本空間 | sample space | $\Omega$ | 標本点のすべての集合 |
| 事象 | event |  | 標本空間の部分集合 |
| 全事象 | sure event | $\Omega$ | 標本空間と同じ |
| 空事象 | empty event | $\phi$ |  |
| 拝反事象 | mutually exclusive events | $A \cap B=\phi$ | AとBが同時に起きない事象 |
| 和事象 | union of events | ${A}\cup{B}$ | AとBの集合のうち少なくとも一方の事象が起きる事象 |
| 積事象 | intersection of events | ${A}\cap{B}$ | AとBが同時に起きる事象 |
| 余事象 | complement of an event | $\overline{A}$ | 事象Aが起こらないという事象 |
| 確率 | probability | $P(A)$ | 事象Aが起こる確率 |
| 条件付き確率 | conditional probability | $P(A\|B)$ | Bの条件のもと事象Aが起こる確率 |

## 標本空間と事象について

コイン投げで考えます。

コインを1回投げた試行の結果を「裏：0、表：1」とおきます。

このとき、

標本空間は $\Omega=\{ {0,1}\}$ となります。

事象は $\omega=\{0,1\},\{0\},\{1\},\phi$ の4つとなります。

事象は「標本空間の部分集合」のことです。

$\{0,1\}$ は $0$ もしくは $1$ が出た場合の部分集合と考えれば良いです。

## 事象に関する法則および性質
### 和事象・積事象の分配法則

$$\begin{aligned}
({A}\cap{B})\cup{C} &= ({A}\cup{C})\cap({B}\cup{C})\\
({A}\cup{B})\cap{C} &= ({A}\cap{C})\cup({B}\cap{C})
\end{aligned}$$

### ド・モルガンの法則

$$\begin{aligned}
\overline{ {A}\cap{B}} = {\overline{A}}\cup{\overline{B}}\\
\overline{ {A}\cup{B}} = {\overline{A}}\cap{\overline{B}}
\end{aligned}$$

### 加法定理

$$\begin{aligned}
& P\left( A\cup B\right) =P\left( A\right) +P\left( B\right) -P\left( A\cap B\right)\\
& P\left( A\cup B\right) =P\left( A\right) +P\left( B\right) & \cdots (A \cap B=\phi のとき)
\end{aligned}$$

### 条件付き確率
ある事象 $A$ について別の事象 $B$ が起こったときの事象 $A$ が起こる確率を、 $B$ を条件とする $A$ の条件付確率といいます。

$$
P\left( A | B\right) = \dfrac{P\left( A\cap B\right) }{P\left( B\right) }
$$

#### 乗法定理

条件付き確率の公式を組み替えると作れます。

$$
P\left( A\cap B\right) = P\left( A | B\right) \cdot P\left( B\right)
$$

### 独立性

ある事象 $A$ において別の事象 $B$ に事象 $A$ が起こる確率が左右されない場合、この二つの事象は独立しているといいます。

$$
P\left( A | B\right) = P(A)
$$

このとき乗法定理は下記となります。

$$
P\left( A\cap B\right) = P(A) \cdot P\left( B\right)
$$

## 参考文献

- 東京大学教養学部統計学教室『統計学入門 (基礎統計学Ⅰ) (日本語) 単行本 – 1991/7/9』
