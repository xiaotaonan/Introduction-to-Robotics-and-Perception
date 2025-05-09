# 3.4.8. HMM 的 max-product 算法

> HMM 上的 Max-product，也称为 Viterbi 算法，是一种用于查找 MAP 估计值的动态规划算法。

在本节中，我们讨论了一种比 naive 算法快得多的算法来查找 MAP 估计值。给定大小$$n$$的 HMM 因子图 ，最大乘积算法是一种$$O(n)$$用于查找 MAP 估计值的算法，GTSAM 在后台使用该算法。

让我们使用图 4 中的例子来理解它背后的主要思想。要查找$$X$$我们需要最大化产品的 MAP 估计值

$$\phi (X_1,X_2,X_3) = \prod \phi_i (X_i)$$（公式3.32）

即因子图的值。因为这是因子值的乘积，所以我们可以递归计算它的最大值 - 动态编程风格。我们首先显式写出最大化积：

$$
\begin{equation}
\max_{\mathcal{X}} \prod\phi_{i}(\mathcal{X}_{i}) = 
\max_{X_1, X_2, X_3} ~~~\phi_1(X_1)\phi_2(X_1)\phi_3(X_1, X_2) \phi_4(X_2)\phi_5(X_2, X_3)\phi_6(X_3) 
\end{equation}
$$

递归的关键是依次考虑每个变量，从$$X_1$$开始。特别是，让我们将所有与$$X_1$$

$$
\begin{equation}
\max_{\mathcal{X}} \prod\phi_{i}(\mathcal{X}_{i}) = 
\max_{X_1, X_2, X_3} ~~~ \{ \phi_1(X_1)\phi_2(X_1)\phi_3(X_1, X_2) \} ~~~ \phi_4(X_2)\phi_5(X_2, X_3)\phi_6(X_3)
\end{equation}
$$

这允许我们在内部移动最大运算符超过$$X_1$$：

$$
\begin{equation}
\max_{\mathcal{X}} \prod\phi_{i}(\mathcal{X}_{i}) = 
\max_{X_2, X_3} ~~~ \{ \max_{X_1} \phi_1(X_1)\phi_2(X_1)\phi_3(X_1, X_2) \} ~~~ \phi_4(X_2)\phi_5(X_2, X_3)\phi_6(X_3)
\end{equation}
$$

递归的关键在于，我们可以简单地将大括号内的表达式视为 on 的新因子 ，$$X_2$$定义为

$$
\begin{equation}
\tau(X_2)\doteq \max_{X_1} \phi_1(X_1)\phi_2(X_1)\phi_3(X_1, X_2),
\end{equation}
$$

，它记录仅最大化$$X_1$$产生的最大值。计算的值取决于$$X_2$$的值，因为$$X_2$$涉及因子$$\phi_3$$。然而，至关重要的是，变量$$X_3$$不参与最大化。

将新因子代入最大化，我们现在需要最大化不再是$$X_1$$函数的简化因子图 ，

$$
\begin{equation}
\max_{\mathcal{X}} \prod\phi_{i}(\mathcal{X}_{i}) =
\max_{X_2, X_3} ~~~\tau(X_2) \phi_4(X_2)\phi_5(X_2, X_3)\phi_6(X_3)
\end{equation}
$$

这允许我们递归，直到没有更多的变量留下！

对于隐马尔可夫模型，这种动态规划方法称为 Viterbi 算法。请注意，上面的算法草图仅产生因子图的最大值。Viterbi 算法的一个关键部分是添加一些记账，以便在递归终止后，我们可以恢复使因子图达到其最大值的实际变量赋值。此外，HMM 的 max-product 的复杂度在节点数量上是线性的，这与指数复杂度相比是一个很好的改进。每个排除步骤的复杂度在状态数上都是二次方的，因为我们必须形成乘积因子，然后最大化它们。

因为在每一步中，都会从最大化中消除一个变量，所以 max-product 算法实际上是消除算法的一个实例，它适用于任意因子图，尽管不一定是时间上的$$O(n)$$。事实上，max-product（以及下面的 sum-product）可以比 HMM 中的线性链更通用地应用。虽然我们不会在这里更详细地讨论这种联系，但消除算法在许多其他情况下都会出现，它本身就值得一本书。
