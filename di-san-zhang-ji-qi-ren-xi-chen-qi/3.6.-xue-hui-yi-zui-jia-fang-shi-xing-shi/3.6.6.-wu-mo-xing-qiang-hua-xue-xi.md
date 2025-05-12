# 3.6.6. 无模型强化学习

> 您只需要 Q。

另一种不同的无模型方法是 Q 学习。在上面，我们试图通过估计 （大型） 过渡和奖励表来对世界进行建模。但是，请记住上一节中，有一个小得多的 Q 值$$Q(x,a)$$表也允许我们采取最佳行动。这是因为我们可以从最佳 Q 值$$Q^*(x,a) \approx Q(x,a;V^*)$$计算最佳策略$$\pi ^*(x)$$：

$$
\begin{equation}
\pi^*(x) = \arg \max_a Q^*(x,a).
\end{equation}
$$

这就提出了一个问题，即我们是否可以简单地学习 Q 值，这可能更有效的样本效率。换句话说，我们将使用更少的训练数据获得更准确的值，因为我们要估计的数量更少。

为此，请记住 Bellman 方程可以写为

$$
\begin{equation}
V^*(x) = \max_a Q^*(x,a)
\end{equation}
$$

允许我们将上面的 Q 值改写为

$$
\begin{equation}
Q^*(x,a) = \sum_{x'} P(x'|x, a) \{ R(x,a,x') + \gamma \max_{a'} Q^*(x',a') \}
\end{equation}
$$

这为我们提供了一种估计 Q 值的方法，因为我们可以使用 Monte Carlo 估计值来近似上述值，并总结我们的经验：

$$
\begin{equation}
Q^*(x,a) \approx \frac{1}{N(x,a)} \sum_{x,a,x'} R(x,a,x') + \gamma \max_{a'} Q^*(x',a')
\end{equation}
$$

不幸的是，上述估计值取决于最佳 Q 值。因此，最终的 Q-learning 算法通过新旧估计之间的 “alpha 混合” 逐渐应用此估计，这也对奖励进行平均：

$$
\begin{equation}
\hat{Q}(x,a) \leftarrow (1-\alpha) \hat{Q}(x,a) + \alpha \{R(x,a,x') +  \gamma \max_{a'} \hat{Q}(x',a') \}
\end{equation}
$$

在代码中：

```python
alpha = 0.5 # learning rate
gamma = 0.9 # discount factor
Q = np.zeros((5, 4), float)
for x, a, x_prime, r in data:
    old_Q_estimate = Q[x,a]
    new_Q_estimate = r + gamma * np.max(Q[x_prime])
    Q[x, a] = (1.0-alpha) * old_Q_estimate + alpha * new_Q_estimate
print(Q)
```

```python
[[78.06708893 78.754749   76.50549984 74.96116896]
 [67.86544097 56.0889752  56.35949553 45.90217779]
 [30.61778741 50.34640371 30.75452121 33.18299242]
 [41.54212305 53.19523855 71.23601338 59.31847172]
 [55.25744421 48.64301805 56.53929042 45.06541913]]
```

这些值还不是很准确，因为您可以通过更改上面的体验数量来确定自己，但请注意，在我们收敛之前就可以实现最佳策略。
