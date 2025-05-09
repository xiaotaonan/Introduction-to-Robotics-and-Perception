# 2.6.3 拟合高斯

回想一下，高斯分布完全由两个参数指定：平均值$$\mu$$和方差$$\sigma^2$$。

如果我们观察到怀疑是由高斯密度生成的连续数据，那么我们可以轻松地通过以下方式计算平均值$$\mu$$的估计值。

$$\hat \mu=\frac{1}{N}\sum_i x_i$$（公式 2.46）

估计值$$\hat \mu$$有时也称为经验平均值。我们需要的另一个参数是方差$$\sigma^2$$，它定义为与平均值的平方偏差的期望值：

$$E[(x-\mu)^2]$$（公式2.47）

在我们获得经验平均值$$\hat \mu$$之后，可以通过以下方式估计方差：

$$\hat \sigma^2=\frac{1}{N-1}\sum_i (x_i-\hat \mu)^2$$（公式2.48）

标准差$$\sigma$$定义为方差的平方根，因此标准差的估计值由下式给出：

$$\hat \sigma = \sqrt{\hat {\sigma^2}}$$（公式 2.49）

注意：上面我们除以$$N-1$$而不是$$N$$。通俗地说，原因是我们已经通过估计样本的平均值“用掉”了一个数据点，我们对此进行校正以获得方差的“无偏”估计。

下面是一些使用 `numpy` 库实现此目的的 Python 代码。首先，我们根据已知均值和标准差的高斯分布生成一些“数据”。

```
mean = 200  # grams, say...
stddev = 50  # also in grams
N = 200  # number of samples
data = np.random.normal(mean, stddev, N)
```

当我们绘制直方图时，我们可以看到典型的“钟形曲线”形状出现（尝试增加 N），如图 3 所示。

```
#| caption: Histogram of the generated data.
#| label: fig:histogram-of-generated-data
nbins = N//10
px.histogram(x=data, nbins=nbins)
```

<figure><img src="../../../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

样本均值很容易用 `np.mean` 计算：

```
mu_hat = np.mean(data)
mu_hat
```

```
201.6866593433805
```

```
np.var(data, ddof=1)
```

```
2388.152838995407
```

请注意，对于 200 个样本，尽管直方图相当“混乱”，但样本均值$$\hat \mu$$接近真实均值$$\mu=200$$。

还有一个函数 `np.var` 可以计算样本方差，但我们需要注意提供 `ddof=1` 参数来获取无偏估计值（执行 `help(np.var)` 了解更多信息）。

以下是计算方差的代码：

```
var_hat = np.sum(np.square(data-mu_hat))/(N-1)
var_hat
```

```
2388.152838995407
```

通过取平方根，我们发现它与我们的基本事实标准差$$\sigma$$非常吻合：

```
sigma_hat = np.sqrt(var_hat)
print(sigma_hat)
```

```
48.86873068737725
```
