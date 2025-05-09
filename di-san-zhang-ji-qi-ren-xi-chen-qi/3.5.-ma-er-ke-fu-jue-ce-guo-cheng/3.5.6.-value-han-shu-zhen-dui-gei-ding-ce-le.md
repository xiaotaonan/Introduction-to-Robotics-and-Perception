# 3.5.6. Value 函数（针对给定策略）

> value 函数 $$\mathcal{V}^{\pi}$$> 在给定 policy $$\pi$$> 下测量每个状态的 expectedutility 。

我们现在想描述任何给定策略的质量。上面，我们将特定$$n$$作序列的效用定义为

$$
\begin{equation}
U(a_1, \dots, a_n, x_1, \dots x_{n+1}) =
R(x_1,a_1, x_2) + \gamma R(x_2, a_2, x_3) + \dots \gamma^{n-1} R(x_{n}, a_{n}, x_{n+1})
\end{equation}
$$

并使用预期的效用作为$$E[U(a_1,\dots,a_n,X_1,\dots X_{}n+1)]$$\
特定动作序列功效的定量衡量标准。我们可以将相同类型的推理应用于策略$$\pi$$。在评估保单时，通常会在无限时间范围内使用折扣奖励。在这种情况下，我们将 policy $$\pi$$的 value 函数 $$\mathcal{V}^{\pi}：\mathcal{X} \rightarrow R$$定义为

$$
\begin{equation}
V^\pi(x_1) \doteq E [R(x_1, \pi(x_1), X_2) + \gamma R(X_2, \pi(X_2), X_3) + \gamma^2 R(X_3, \pi(X_3), X_4) + \dots]
\end{equation}
$$

其中，期望被接管了 states $$X_2,X_3 \dots$$的可能值。请注意，该策略$$\pi$$是确定性的，但这是$$\pi(X_i)$$\
将确定性策略应用于随机状态$$X_i$$所产生的随机作。

策略的 value 函数可以以很好的递归形式编写，该格式可以通过以下派生获得。

$$
\begin{equation}
\begin{aligned}
V^\pi(x_1) &=
E [R(x_1, \pi(x_1), X_2) + \gamma R(X_2, \pi(X_2), X_3) + \gamma^2 R(X_3, \pi(X_3), X_4) + \dots] \\
&= \sum_{x_2} P(x_2|x_1, \pi(x_1)) R(x_1, \pi(x_1), x_2) \\
& + \sum_{x_2} P(x_2|x_1, \pi(x_1)) E [\gamma R(x_2, \pi(x_2), X_3) + \gamma^2 R(X_3, \pi(X_3), X_4) + \dots]\\
&= \sum_{x_2} P(x_2|x_1, \pi(x_1)) \{R(x_1, \pi(x_1), x_2) + \gamma V^\pi(x_2)\}
\end{aligned}
\end{equation}
$$

其中第二行是通过显式写入对随机状态$$X_2$$的期望求和获得的，第三行是通过注意到$$E[\gamma R(x_2,\pi(x_2),X_3)+\gamma ^2 R(X_3,\pi(X_3),X_3)+ \dots ]= \gamma  \mathcal{V}^{\pi}(x_2)$$而获得的。

我们可以将 distributivity 属性应用于这个表达式，以获得

$$
\begin{equation}
\begin{aligned}
V^\pi(x_1) &= \sum_{x_2} P(x_2|x_1, \pi(x_1)) R(x_1, \pi(x_1), x_2) + \gamma  \sum_{x_2} P(x_2|x_1, \pi(x_1))  V^\pi(x_2) \\
&= \bar{R}(x_1,\pi(x_1)) + \gamma \sum_{x_2} P(x_2|x_1, \pi(x_1)) V^\pi(x_2)
\end{aligned}
\end{equation}
$$

其中 term $$\overline{R}(x_1,\pi(x_1))$$是 在 state $$x_1$$中应用动作$$a=\pi(x_1)$$的预期奖励 ，我们已经知道如何从 reward 函数 $$R$$和转换概率中计算。现在，通过替换 x $$x_1$$，和 $$x^{\prime}$$for$$x_2$$我们可以推广此表达式以在任何任意时间应用于状态$$x$$：

$$
\begin{equation}
V^\pi(x) = \bar{R}(x,\pi(x)) + \gamma \sum_{x'} P(x'|x, \pi(x)) V^\pi(x')
\end{equation}
$$

这有一个非常好的解释：在给定策略下，一个状态的值是该策略下的预期奖励$$\overline{R}(x,\pi(x))$$\
，加上下一个状态时价值函数的贴现期望值。
