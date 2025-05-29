# 3.2.4. 受控马尔可夫链

> 马尔可夫链无处不在。作控制它们。

在上面的信念转换函数的推导中，我们采用了时间解耦属性，即，给定时间步$$b_{k+1}$$\
的状态，在时间步$$k$$之前应用的所有动作都与确定信念状态$$b_{k+1}$$无关。这是所谓的马尔可夫属性的一个例子。此属性的变体对于减少在很长一段时间内进行概率推理所需的计算量至关重要。

此属性的最常见示例出现在称为马尔可夫链的系统中。在最简单的形式中，aMarkov 链是一个随机变量序列，$$X_1,X_2,\dots$$对于每个$$k$$，我们有：

$$P(X_{k+1}|X_1 \dots X_k)=P(X_{k+1}|X_k)$$。（公式3.11）

对于马尔可夫链，知识$$X_k$$将过去（即$$X_1 \dots X_{k-1}$$）与未来 （即 ）完全解耦$$X_{k+1}$$\
。因此，在推理未来状态时，我们不需要对系统的整个历史进行计算：如果我们知道$$X_k$$\
，我们只需要在推理未来时执行与现在相关的计算。

马尔可夫链有一个很好的图形表示。每个节点对应一个随机变量，有向边指定条件概率。Asan 应用程序，我们可以使用这个简单的图形模型来表示状态之间的概率转换，实际上它可以在代码中生成，如图 6 所示。

```python
#| caption: A simple three state Markov chain.
#| label: fig:markov_chain_3
N = 3
X = VARIABLES.discrete_series("X", range(1, N+1), vacuum.rooms) # states for times 1...N
markov_chain = gtsam.DiscreteBayesNet()
markov_chain.add(state_prior)
for k in range(1, N):
    markov_chain.add(X[k+1], [X[k]], "6/1/1/1/1 1/6/1/1/1 1/1/6/1/1 1/1/6/1/1 1/1/1/1/6")
show(markov_chain, hints={"X":1})
```

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

此图中的每个节点都表示一个随机变量，因此每个节点都具有关联的概率分布。如果我们知道 初始状态$$X_1$$的分布，我们就可以 通过评估与图中有向边关联的条件分布，递归计算 all $$k >1$$的状态$$X_k$$分布。

我们的机器人吸尘器比这个简单的马尔可夫链稍微复杂一些，因为机器人具有执行动作的能力，而这些动作会影响概率在链中的传播。这种类型的系统被称为受控马尔可夫链，因为它将控制输入（动作）合并到通常的马尔可夫链中。

从图形上讲，我们可以通过增强上图以包含表示 actions 的节点来表示这样的系统。我们使用 abox 来表示其值已知的节点。由于机器人知道它执行哪些作，因此作节点用框表示。对于我们的扫地机器人，我们也知道初始状态的值，因为机器人总是从办公室开始。因此，我们还使用一个框来表示此图中的初始状态。

Asan 示例中，图 7 中的代码为我们系统的单个步骤（即直到时间步长$$k=2$$）构建了受控马尔可夫链。

```python
#| caption: A Bayes net fragment modeling the effect of an action on the state.
#| label: fig:bayes_net_fragment
action_prior = gtsam.DiscreteDistribution(A[1], "1/1/1/1")
fragment = gtsam.DiscreteBayesNet()
fragment.add(motion_model)
show(fragment, hints={"A": 2, "X": 1}, boxes={A[1][0], X[1][0]})
```

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

通过应用上面的信念转换方程，我们可以计算 的后验概率$$P(X_2|a_1)$$，$$X_2$$因为动作$$a_1$$\
和初始状态$$x_1$$都是完全已知的。给定父变量$$A_1$$和$$X_1$$的值，我们可以检查相应的转换概率。

图 8 中的代码显示了如何使用我们在本节前面定义的变量 `motion_model` 来实现这一点。在这个例子中，如果我们从 开始$$x1=Office$$并尝试向右走，即 action $$a_1=R$$ ，我们得到下一个状态$$X2$$ 的概率 ，表明我们以 80% 的概率移动到走廊，以 $$20\%$$的概率留在办公室。

```python
#| caption: The result of applying the motion model to a specific state and action.
#| label: fig:apply_motion_model
values = VARIABLES.assignment({X[1]: "Office", A[1]: "R"})
pretty(motion_model.choose(values))
```

|      X2     | Value |
| :---------: | :---: |
| Living Room |   0   |
|   Kitchen   |   0   |
|    Office   |  0.20 |
|   Hallway   |  0.80 |
| Dining Room |   0   |

这个想法可以扩展到任意多个 actions ，只需为每个时间步$$k$$添加 action 和 state 节点。图 9 中的代码显示了一个代码示例，其中我们创建了一个具有三种状态的受控马尔可夫链。

```python
#| caption: Concatenating Bayes net fragments into a controlled Markov chain.
#| label: fig:controlled_markov_chain
A = VARIABLES.discrete_series("A", range(1, N), vacuum.action_space) # actions for times 1...N-1
bayesNet = gtsam.DiscreteBayesNet()
bayesNet.add(state_prior)
for k in range(1, N):
    bayesNet.add(X[k+1], [X[k], A[k]], vacuum.action_spec) # add creates conditional and adds
show(bayesNet, hints={"A":2, "X":1}, boxes={A[1][0],A[2][0]})
```

<figure><img src="../../../.gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

该示例仅显示了由三态代码片段生成的图形模型。在这个两步示例中，如何获得 posteriorover  $$X_3$$尚不清楚。我们将在下面探讨。
