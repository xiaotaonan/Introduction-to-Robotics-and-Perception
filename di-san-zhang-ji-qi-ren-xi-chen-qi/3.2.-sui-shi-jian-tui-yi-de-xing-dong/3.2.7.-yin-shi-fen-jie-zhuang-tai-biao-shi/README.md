# 3.2.7. 因式分解状态表示

> 我们可以通过因式分解状态来节省更多。

如果可以使用彼此相对独立的特征来描述机器人的状态，则分解状态表示非常有用。继续我们的示例，机器人真空吸尘器也可能耗尽电池电量，因此我们可以将不同的变量与其电池状态相关联，例如 `empty` 、 、 `half` 或 `full` 。然后，机器人的状态将由两个变量的组合来指定：机器人所在的房间及其电池状态。请注意，现在可能状态的总数是组合的：如果有 5 个房间和 3 个不同的电池电量，则机器人总共有 15 种可能的状态。

电池寿命的一个可能模型可以是以下转换表，它与采取的作无关，并且将始终从 `full` to `half` ，然后从 to `half` `empty` ，当然，一旦电池耗尽，它将保持为空：

```python
battery_states = ["full", "half", "empty"]
B = VARIABLES.discrete_series("B", range(1,N+1), battery_states)
spec_b = "9/1/0 0/9/1 0/0/1 "
pretty(gtsam.DiscreteConditional(B[2], [B[1]], spec_b))
```

|   B1  | full | half | empty |
| :---: | :--: | :--: | :---: |
|  full |  0.9 |  0.1 |   0   |
|  half |   0  |  0.9 |  0.1  |
| empty |   0  |   0  |   1   |

图形模型方法使我们能够轻松地将概率作扩展到因式分解的状态表示。图 12 中的代码显示了一种方法。

```python
#| caption: A factored Bayes net for the vacuum cleaner problem.
#| label: fig:factored_bayes_net
factored = gtsam.DiscreteBayesNet()
factored.add(state_prior)
factored.add(B[1], [], "1/0/0") # initial battery state
for k in range(1, N):
    factored.add(X[k+1], [X[k], A[k]], vacuum.action_spec) # motion model for location
    factored.add(B[k+1], [A[k], B[k]], "".join([spec_b]*4)) # battery evolution model

show(factored, hints={"A":2, "X":1, "B":0}, boxes={A[1][0],A[2][0]})
```

<figure><img src="../../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

你可以看到，在选择的转换模型下，现在有马尔可夫链，当给定动作序列时，这些链是独立的。
