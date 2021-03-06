# 布尔代数

## 基本概念

设 B 是一个非空集合，具有二元运算 + 和 *，一元运算`和两个不同的元素0，1，若对于任意的 a, b, c \in B，以下公理成立，则称 B 为一个布尔代数：
交换律： a + b = b + a,
        a * b = b * a
分配律： a + (b * c) = (a + b) * (a + c),
        a * (b + c) = (a * b) + (a * c)
单位元律： a + 0 = a, a * 1 = a
互补律： a + a' = 1, a * a' = 0

当我们要强调其六个部分时，用(B, +, *, ', 0, 1)来表示一个布尔代数，称 0 为零元素，1 为单位元素，a' 为 a 的补。

运算 +, * 与 ' 分别称为 和，积，与补。
优先级：' 运算优先于 * 优先于 +。

### 子代数，同构的布尔代数

子代数：设 C 是布尔代数 B 的一个非空子集，如果 C 本身是布尔代数（相对于 B 的运算），我们说称 C 是 B 的一个子代数。
注意 C 是 B 的一个子代数当且仅当 C 对于 B 中的三种运算，都是封闭的。

同构：两个布尔代数 B 和 B' 称为同构的，如果有一一对应（双射）f: B \to B'，并保持这三种运算，即使得对于 B 中任意元素 a 和 b，有：
$$
f(a + b) = f(a) + f(b), f(a * b) = f(a) * f(b), f(a') = f(a)'
$$

## 对偶性

在布尔代数中，任意命题的对偶是由在原命题中交换运算 + 和 *，并交换单位元 0 和 1 得到的命题。

**对偶原理** 任何布尔代数的真命题的对偶仍是真命题。

## 布尔代数的基本定理

**定理15.2** 设 a, b, c 是布尔代数 B 中的任意元素，

  1. 幂等律
     a + a = a, a * a = a
  2. 有界律
     a + 1 = 1, a * 0 = 0
  3. 吸收律
     a + (a * b) = a, a * (a + b) = a
  4. 结合律
     (a + b) + c = a + (b + c), (a * b) * c = a * (b * c)

**定理15.2** 设 a 是布尔代数 B 中的任意元素，

  1. 补的唯一性
     a + x = 1 \land a * x = 0 \implies x = a'
  2. 对合律
     (a')' = a
  3. 0' = 1, 1' = 0


**DeMorgan律**

(a + b)' = a' * b', (a * b)' = a' + b'

## 作为格的布尔代数

由于每个布尔代数都满足结合律，交换律和吸收律，因此它是一个格。并且，+ 和 * 分别为 \lor 和 \land 运算。
相对这个格，对于任意元素 a \in B，a + 1 = 1 蕴含 a <= 1，而 a * 0 = 0 蕴含 0 <= a。于是，B 是一个有界格。
此外，B 也是一个分配格和有补格。反之，每个有界的，分配的，有补的格 L 也满足布尔代数的定义。

**替换定义** 一个布尔代数 B 是一个有界的、分配的、有补的格。反之。

定理15.5 在布尔代数中，下列条件是等价的：
  1. a  + b = b,  2. a * b  = a
  3. a' + b = 1,  4. a * b' = 0
这样，在布尔代数中，只要知道上列四个条件之一是正确的话，我们就可以写 a <= b。

## 表示定理

设 B 是一个有限的布尔代数，A 是 B 的原子的集合，且 P(A) 是原子集 A 的所有子集的布尔代数。

函数 f: B \to P(A) 表示：
$$
f(x) = { a_1, a_2, \cdots, a_r }
$$

**定理15.6** 映射 f: B \to P(A) 是一个同构映射。

**推论15.7** 一个有限的布尔代数有 2^n 个元素，n 为正整数
因此，布尔代数至少有 2 个元素。

## 集合的积和式

## 布尔代数的积和式

**定义** 若布尔表达式 E 是一个基本积或是两个更多基本积的和，且这些积是互不包含的，这样的一个布尔表达式 E 被称为**积和表达式**。

**定义** 设 E 是任意的布尔表达式，E 的一个**积和式**是一个等价的布尔积和表达式。

**定理** 每个非零元的布尔表达式 E = E(x1, x2, ..., xn)等价于唯一的完全积和表达式。

## 极小布尔表达式，素隐项

### 极小的积和式

我们说 E 是极小的，如果没有比 E 简洁的等价的积和表达式。（可能有不止一种极小积和表达式）

### 素隐项

一个基本积 P 被称作一个布尔表达式 E 的素隐项，若：
$$
P + E = E
$$

且 P 中不包含齿条这个性质的其他基本积。

**定理** 一个布尔表达式 E 的极小积和表达式是 E 的素隐项的和。

### 基本积的共识

**引理** 假设 Q 是 P1 和 P2 的共识，那么
$$
P_1 + P_2 + Q = P_1 + P_2
$$
