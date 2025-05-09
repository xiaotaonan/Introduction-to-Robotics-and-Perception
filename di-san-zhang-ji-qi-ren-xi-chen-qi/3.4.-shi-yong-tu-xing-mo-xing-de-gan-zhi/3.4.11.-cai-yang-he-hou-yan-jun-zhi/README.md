# 3.4.11. 采样和后验均值\*

> 贝叶斯推理处于最佳状态。

当我们可以从 后验$$P(X|Z)$$中产生样本$$X^{(s)}$$时，我们可以计算任何实值函数$$f(X)$$的经验平均值，如下所示，

$$
\begin{equation}
E_{P(\mathcal{X}|\mathcal{Z})}[f(x)]\approx \frac{1}{N}\sum f(\mathcal{X}^{(s)}),
\end{equation}
$$

其中$$N$$是样本数。例如，我们可以使用这种方法计算机器人行进距离的后验平均值，无论是欧几里得距离还是曼哈顿距离。这样做将提供比仅计算 MAP 值的距离更可靠的估计，因为这种方法对整个概率分布进行平均，而不仅仅是使用单个（尽管是最可能的）估计。

例如，下面的代码对 1000 个备用状态历史记录进行了采样，这些历史记录是可能发生的情况的平行宇宙：

```python
counts = np.zeros((3, 5))
num_samples = 1000
for i in range(num_samples):
    sample = posterior.sample()
    for k in range(1,3+1):
        key = X[k][0]
        room_index = sample[key]
        counts[k-1][room_index] += 1 # base 0!
```

后验意味着为我们提供了一种方法，以某种方式总结这 1000 个架空历史，而不仅仅是将它们全部打印出来。一个想法是总结每个时间步长在特定房间中的概率。事实证明，我们可以使用单行代码来做到这一点，因为我们在上面的代码中保留了 count 的 track：

```python
pd.DataFrame(data=100*counts/num_samples,
             index=range(1, N+1), columns=vacuum.rooms)
```

|     | Living Room | Kitchen | Office | Hallway | Dining Room |
| :-: | :---------: | :-----: | :----: | :-----: | :---------: |
|  1  |     3.3     |   1.4   |   3.8  |   80.6  |     10.9    |
|  2  |     0.9     |   3.9   |   0.8  |   5.0   |     89.5    |
|  3  |     5.9     |   90.7  |   0.8  |   0.0   |     2.6     |

这些近似的边际表示机器人在特定时间步长处于特定房间的可能性有多大。这是比 MAP 值中可用的信息更丰富的信息，MAP 值只是轨迹的点估计。
