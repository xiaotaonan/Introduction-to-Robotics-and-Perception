# 3.3.1. 传感器模型

> 一个简单的光传感器。

本章主要关注动作，因此我们将考虑的感知相当简单。让我们设想一个简单的光传感器，我们可以用它来作为机器人在哪个房间的线索。具体来说，为了说明起见，让我们假设客厅和厨房在南侧，因此在典型的一天中光线充足。办公室和餐厅位于北侧，光传感器通常会以中等光照水平响应。另一方面，走廊非常黑暗，因为它的窗户很少。我们可以通过条件概率分布$$P(Z_t|X_t)$$来捕获这些语义，其中$$X_t$$$$P(Z_t|X_t)$$是和以前一样在时间$$t$$上的状态，是$$Z_t \in \{dark,medium,light\}$$测得的光水平。

图 1 中的小代码片段是创建合理传感器模型的一种方法。

```python
#| caption: Creating a sensor model $P(Z_t|X_t)$ using a string-based specification.
#| label: fig:vacuum-sensor-spec
# vacuum.light_levels = ["dark", "medium", "light"]
Z = VARIABLES.discrete_series("Z", range(1, N+1), vacuum.light_levels) # define variables
# vacuum.sensor_spec = "1/1/8 1/1/8 2/7/1 8/1/1 1/8/1"
pretty(gtsam.DiscreteConditional(Z[1], [X[1]], vacuum.sensor_spec)) # CPT on Z1 at time t=1
```

|      X1     | dark | medium | light |
| :---------: | :--: | :----: | :---: |
| Living Room |  0.1 |   0.1  |  0.8  |
|   Kitchen   |  0.1 |   0.1  |  0.8  |
|    Office   |  0.2 |   0.7  |  0.1  |
|   Hallway   |  0.8 |   0.1  |  0.1  |
| Dining Room |  0.1 |   0.8  |  0.1  |

有几件事需要注意。

* 这又是一个离散传感器;我们之前在第 2 章中遇到过这些问题。
* 它是一个不完美的传感器，因此每个房间都有一个最可能的结果，但所有结果在所有房间都是可能的。
* 上面的 CPT（条件概率表）还捕获了建模问题，例如全天光线水平的变化。
