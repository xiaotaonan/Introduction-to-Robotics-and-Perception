# 2.6.1 估计离散 PMF

> 计算每个类别的出现次数。

在第 2.1 节中，我们引入了概率质量函数 (PMF) 的概念，用于表征处于特定状态的先验概率。事实证明，通过长期观察状态获得的归一化计数可以很好地近似 PMF。输入的样本越多，近似效果越好。

举个例子，假设我们在不同的垃圾分类区观察一段时间，并记录每件垃圾的类别。我们可能会看到类似这样的情况：

```
data = [1, 1, 1, 2, 1, 1, 1, 3, 0, 0, 0, 1,
        2, 2, 2, 2, 4, 4, 4, 1, 1, 2, 1, 2, 1]
```

使用 `numpy` ，我们可以通过 `bincount` 函数获取计数。然后，我们使用 `plotly.express` 绘制计数，如图 1 所示。

```
#| caption: Counts of each category in the data.
#| label: fig:counts_of_categories
counts = np.bincount(data)
px.bar(x=categories, y=counts)
```

<figure><img src="../../../.gitbook/assets/image (8).png" alt=""><figcaption><p>图1</p></figcaption></figure>

然后，我们可以通过将计数$$N_k$$除以数据点的数量$$N$$来估算每个类别$$c_k$$的概率：

$$P(x_k) \approx \frac{N_k}{N}$$（公式 2.45）

在我们的例子中：

```
estimated_pmf = counts/sum(counts)
print(f"Counts: {counts}\nEstimated PMF: {estimated_pmf}")
```

```
Counts: [ 3 11  7  1  3]
Estimated PMF: [0.12 0.44 0.28 0.04 0.12]
```

我们现在可以轻松地将其转换为 GTSAM 离散先验，以便进行漂亮的打印：

```
prior = gtsam.DiscreteDistribution(Category, estimated_pmf)
pretty(prior, variables)
```

<table><thead><tr><th>Category</th><th align="center" valign="middle">Value</th></tr></thead><tbody><tr><td>cardboard</td><td align="center" valign="middle">0.12</td></tr><tr><td>paper</td><td align="center" valign="middle">0.44</td></tr><tr><td>can</td><td align="center" valign="middle">0.28</td></tr><tr><td>scrap metal</td><td align="center" valign="middle">0.04</td></tr><tr><td>bottle</td><td align="center" valign="middle">0.12</td></tr></tbody></table>

请注意，计数是估算 PMF 所需的唯一数量：统计学家会说，计数对于估算概率分布而言是充分统计量。实际上，GTSAM 可以直接采用计数本身，因为它内部进行了归一化：

```
prior = gtsam.DiscreteDistribution(Category, "3/11/7/1/3")
pretty(prior, variables)
```

| Category    | Value |
| ----------- | :---: |
| cardboard   |  0.12 |
| paper       |  0.44 |
| can         |  0.28 |
| scrap metal |  0.44 |
| bottle      |  0.12 |
