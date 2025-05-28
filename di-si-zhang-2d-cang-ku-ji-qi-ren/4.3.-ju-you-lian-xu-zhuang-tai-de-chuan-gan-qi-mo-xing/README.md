# 4.3. 具有连续状态的传感器模型

> 从高斯传感器到非高斯传感器。

在前面的章节中，我们使用了可以用相对简单的概率模型来描述的传感器，无论是离散条件概率分布（例如，垃圾分拣机器人的导电性和吸尘机器人的光线感应），还是一维高斯分布（例如，垃圾分拣机器人的重量传感器）。在本节中，我们介绍了三种更现实的传感器，它们分别类似于现代机器人系统中经常使用的传感器：

* 一个接近传感器
* 一个 RFID 距离传感器，其具有非线性的测量模型
* 一个类似 GPS 的位置传感器，它使用高斯条件密度。

让我们扩展 4.1 节的示例，一个 100 米 x50 米的仓库，想象有四组货架以等间隔放置。我们可以使用 2D 图像来表示这个场景。我们可以简单地使用 `numpy` 数组来实现，实际上这也是我们采用的方法。这个环境的基础地图定义在 `gtbook.logistics` 。

```python
base_map = logistics.base_map
print("type(base_map):", type(base_map))
print("base_map.dtype:", base_map.dtype)
print("base_map.shape:", base_map.shape)
```

```python
type(base_map): <class 'numpy.ndarray'>
base_map.dtype: float64
base_map.shape: (50, 100)
```

我们将这个 `base_map` 绘制为图像，使用方便定义的 `show_map` 函数，如图 1 所示。

```python
#| caption: The logistics warehouse base map that we use throughout this section.
#| label: fig:logistics_base_map
logistics.show_map(base_map)
```

<figure><img src="../../.gitbook/assets/image (34).png" alt=""><figcaption></figcaption></figure>

在本节的其余部分，我们将展示如何使用这个地图来模拟我们上面列出的三个传感器。
