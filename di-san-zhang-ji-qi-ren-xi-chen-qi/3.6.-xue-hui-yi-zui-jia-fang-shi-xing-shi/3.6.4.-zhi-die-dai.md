# 3.6.4. 值迭代

> 动态规划可用于获得最优值函数。

让我们重述一下贝尔曼方程，该方程必须适用于每种状态$$x$$

$$
\begin{equation}
V^*(x) = \max_a  \left\{ \bar{R}(x,a) + \gamma \sum_{x'} P(x'|x, a) V^*(x')   \right\}.
\end{equation}
$$

如果我们有$$n$$状态，并且由于我们有$$n$$方程，那么我们似乎应该能够求解$$n$$未知值。遗憾的是，它们不是线性方程，因为最大化运算不是线性的。因此，与策略固定的情况不同，我们不能只求解线性方程组来恢复$$V^*$$。

值迭代通过构造一个估计序列来近似$$V^*,V^0,V,^1\dots,V^n$$，该序列收敛到$$V^*$$。从初始猜测开始，$$V^0$$在每次迭代中，我们都会通过 update 规则更新每个状态的 value 函数的近似值：

$$
\begin{equation}
V^{i+1}(x) \leftarrow \max_a \left\{ \bar{R}(x,a) + \gamma \sum_{x'} P(x'|x, a) V^i(x')   \right\} 
\end{equation}
$$

请注意，右侧包含两个项：预期奖励（我们可以精确计算）和一个项 in $$V^i$$（我们当前对 value 函数的最佳猜测）。Value 迭代使用我们当前的最佳猜测$$V^i$$以及已知的预期奖励以迭代方式运行，以更新近似值。与策略迭代不同，我们不希望价值迭代在有限时间内收敛到确切的结果。因此，我们不能使用$$V^{i+1}=V^i$$终止条件。相反，我们经常使用诸如$$|V^{i+1} - V^i| < \epsilon$$， 这样的条件来表示一些较小的值 of $$\epsilon$$作为终止条件。

最后，请注意，我们可以再次使用 Q 值来获取值更新的简要描述：

$$
\begin{equation}
V^{i+1}(x) \leftarrow \max_a Q(x, a; V^i).
\end{equation}
$$

在代码中，这实际上比策略迭代更容易，使用我们上面讨论的简洁的矢量化 Q-table 更新：

```python
V_k = np.full((5,), 100)
for k in range(10):
    Q_k = np.sum(T * (R + 0.9 * V_k), axis=2) # 5 x 4
    V_k = np.max(Q_k, axis=1) # max over actions
    print(np.round(V_k,2))
```

```python
[100.  98.  90.  98.  90.]
[100.    97.64  86.76  97.64  86.76]
[100.    97.58  85.92  97.58  85.92]
[100.    97.56  85.72  97.56  85.72]
[100.    97.56  85.68  97.56  85.68]
[100.    97.56  85.67  97.56  85.67]
[100.    97.56  85.66  97.56  85.66]
[100.    97.56  85.66  97.56  85.66]
[100.    97.56  85.66  97.56  85.66]
[100.    97.56  85.66  97.56  85.66]
```

与 optimal value 函数比较：

```python
print(np.round(optimal_value_function, 2))
```

```python
[100.    97.56  85.66  97.56  85.66]
```

并且我们可以轻松提取最优策略：

```python
Q_k = np.sum(T * (R + 0.9 * V_k), axis=2)
pi_k = np.argmax(Q_k, axis=1)
print(f"policy = {pi_k}")
print([vacuum.action_space[a] for a in pi_k])
```

```python
policy = [0 0 1 2 0]
['L', 'L', 'R', 'U', 'L']
```
