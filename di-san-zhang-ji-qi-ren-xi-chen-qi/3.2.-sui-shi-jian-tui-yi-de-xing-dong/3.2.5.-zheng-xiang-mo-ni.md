# 3.2.5. 正向模拟

> 马尔可夫链的采样。

我们可以在图形模型中使用模拟来探索一系列作可能产生什么结果。因为上面的（受控）马尔可夫链被指定为一组条件分布，并且我们已经看到了如何从中采样，所以我们只需要知道以什么顺序对它们进行采样。事实上：要从条件分布$$p(X|Y)$$中采样，我们需要确保事先对变量$$Y$$进行采样，然后根据$$Y$$的值选择合适的概率分布进行作。然后，我们可以像以前一样使用逆变换采样方法进行。

马尔可夫链中的前向采样只是从左到右连续重复这些步骤，因为这可以确保我们在尝试从条件中采样之前始终具有条件。在给定初始状态$$X_1$$和动作$$a_1,a_2,\cdots$$序列的情况下模拟机器人等效于从此马尔可夫链中采样：

* set $$k=1$$  ，并且 weassume  是已知的。
*   通过对 next state 进行采样来模拟 next action$$A_k x_k{k+1}$$

    的效果 $$x_{x+1} \sim P(X_{k+1}|X_k=x_k,A_k=a_k)。$$（公式3.12）
* 递增$$k$$  并返回到步骤2  。

图 10 说明了如何对此进行编码，并通过以这种方式进行模拟来显示 4 个不同的 rollouts。第 3.5 节 将更详细地讨论推出。

```python
#| caption: A simple example of sampling from a controlled Markov chain.
#| label: fig:sample_markov_chain
def sample(x1, a1, a2):
    values = VARIABLES.assignment({X[1]: x1, A[1]: a1})  # initial state and action
    x2 = vacuum.rooms[bayesNet.at(1).sample(values)]
    values = VARIABLES.assignment({X[2]: x2, A[2]: a2})  # next state and action
    x3 = vacuum.rooms[bayesNet.at(2).sample(values)]
    return [x1, x2, x3]


for i in range(4):
    print(sample("Office", "R", "U"))
```

```
['Office', 'Office', 'Office']
['Office', 'Hallway', 'Hallway']
['Office', 'Hallway', 'Living Room']
['Office', 'Office', 'Office']
```

虽然简单，但从前向模型进行模拟是一项相当重要的技术，是最近深度强化学习取得一些成功的基础，也是 DeepMind 成功击败世界上最好的围棋棋手的基础 \[Silver et al.， 2016]。
