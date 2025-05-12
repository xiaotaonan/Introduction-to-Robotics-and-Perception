# 3.6.2.操作值和最优策略

使用贝尔曼方程，从 给定状态 $$x$$ 计算最优策略 $$\pi^*$$ _很简单 ：_&#x20;

$$
\begin{equation}
\pi^*(x) = \arg
\max_a  \left\{ \bar{R}(x,a) + \gamma \sum_{x'} P(x'|x, a) V^*(x')   \right\}.
\end{equation}
$$

这种计算执行得如此频繁，以至于可以方便地引入所谓的 $$Q$$函数，即对于给定值函数 $$V$$ 而言，处于状态 $$x$$并采取行动 $$a$$ 的值：

$$
\begin{equation} \begin{aligned} Q（x，a;V） \doteq \bar{R}（x，a） + \gamma \sum_{x'} P（x'|x， a） V（x'） \end{aligned} \end{equation}
$$

我们将在本节的许多算法中使用 $$Q$$ 值，下面给出了一种从值函数计算 Q 值的有效方法：

$$Q$$值的另一个名字是操作值，与状态值（即值函数$$V(x)$$）形成对比。Q-函数允许我们简单地编写最优策略$$\pi^*(x)$$，即选择，对于任何给定的状态$$x$$，从最优值函数$$V^*$$计算出具有最高动作值的$$Q(x,a;V^*)$$的动作$$a$$：

$$
\begin{equation}
\pi^*(x) = \arg \max_a  Q(x,a; V^*)
\end{equation}
$$

我们将在本节的许多算法中使用Q-values，下面给出了一种从值函数计算 Q 值的有效方法：

```python
def Q_value(V, x, a, gamma=0.9):
    """Calculate Q(x,a) from given value function"""
    return T[x,a] @ (R[x,a] + gamma * V)
```

使用 `numpy` ，一次计算所有状态-动作对的所有 Q 值的一种非常有效的方法是

```python
Q = np.sum(T * (R + gamma * V), axis=2)
```

我们在下面也会使用。它产生一个大小为$$|X| \times |X|$$ 的矩阵。
