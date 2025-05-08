# 3.3.5. 使用 GTSAM 进行祖先采样

> 代码中的模拟。

当然，GTSAM 内置了进行祖先采样的方法，但它仅适用于反向拓扑排序的贝叶斯网络。这与我们编写 downjoint distributions 的方式相匹配，父级向右，这也是为什么上面我们在 range 上使用 built-in `reversed` ：这是为了确保后面的 state 最后被采样。因为在上面的代码中，我们只指定了$$P(Z_{1:n},X_{1:n}|A_{1:n})$$ ，并且没有明确提供 distributionover 作，所以我们需要给出一个作序列 $$a_{1:n}$$as an 参数。

```python
#| caption: Sampling from the DBN.
#| label: fig:dbn-sample
actions = VARIABLES.assignment({A[k]: "R" for k in range(1,N)})
pretty(dbn.sample(actions))
```

<table><thead><tr><th align="center">Variable</th><th align="center">Value</th><th data-hidden>编码</th></tr></thead><tbody><tr><td align="center">A1</td><td align="center">R</td><td>+</td></tr><tr><td align="center">A2</td><td align="center">R</td><td></td></tr><tr><td align="center">A3</td><td align="center">R</td><td></td></tr><tr><td align="center">A4</td><td align="center">R</td><td></td></tr><tr><td align="center">X1</td><td align="center">Office</td><td></td></tr><tr><td align="center">X2</td><td align="center">Office</td><td></td></tr><tr><td align="center">X3</td><td align="center">Hallway</td><td></td></tr><tr><td align="center">X4</td><td align="center">Dining Room</td><td></td></tr><tr><td align="center">X5</td><td align="center">Dining Room</td><td></td></tr><tr><td align="center">Z1</td><td align="center">dark</td><td></td></tr><tr><td align="center">Z2</td><td align="center">medium</td><td></td></tr><tr><td align="center">Z3</td><td align="center">dark</td><td></td></tr><tr><td align="center">Z4</td><td align="center">medium</td><td></td></tr><tr><td align="center">Z5</td><td align="center">medium</td><td></td></tr></tbody></table>

例如，在图 3 中，我们研究了当我们连续尝试该作 `Right` 4 次时会发生什么。这些作包含在结果 `DiscreteValues` 实例中，因此我们有一个随时间变化的采样 “世界状态” 的完整图片。请注意，除了状态 $$X_k$$ 之外，结果现在还包括每个时间步的 sampledmeasurements $$Z_k$$ 。毫不奇怪，我们很快就从黑暗的走廊过渡到稍微亮一点的餐厅，并被困在那里，因为餐厅右侧没有空间！
