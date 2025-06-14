# 4.2.6. 代码中的高斯 DBN

在 GTSAM 中，使用类 指定高斯密度，该类 `GaussianDensity` 对应于由下式给出的负对数概率

$$
\begin{equation}
\frac{1}{2 \sigma^2} \|x - \mu\|^2.
\end{equation}
$$

使用接受$$\mu$$和$$\sigma$$As 参数的命名构造函数 `FromMeanAndStddev` 。就他们而言，高斯条件密度是使用类 指定的，该类 `GaussianConditional` 对应于由下式给出的负对数概率

$$
\begin{equation}
\frac{1}{2 \sigma^2} \|x - (A_1 p_1 + A_2 p_2 + b)\|^2.
\end{equation}
$$

即，均值 on $$x$$ 是条件变量$$p_1$$ 和 $$p_2$$ 的线性函数。同样，命名构造函数 `FromMeanAndStddev` 可以帮助我们。与往常一样，本节末尾的 GTSAM 101 部分中提供了详细信息。

以上所有内容都用在了下面的代码中，该代码构建了图 6 中的动态贝叶斯网络。

```python
gaussianBayesNet = gtsam.GaussianBayesNet()
A, B = np.eye(2), np.eye(2)
motion_model_sigma = 0.2
for k in reversed(indices[:-1]):
    gaussianBayesNet.push_back(gtsam.GaussianConditional.FromMeanAndStddev(
        x[k+1], A, x[k], B, u[k], [0, 0], motion_model_sigma))
p_x1 = gtsam.GaussianDensity.FromMeanAndStddev(x[1], [20,10], 0.5)
gaussianBayesNet.push_back(p_x1)
```

```python
#| caption: A Gaussian dynamic Bayes net.
#| label: fig:gaussian_bayes_net
position_hints = {'u': 2, 'x': 1}
show(gaussianBayesNet, hints=position_hints, boxes=set(list(u.values())))
```

<figure><img src="../../../.gitbook/assets/image (33).png" alt=""><figcaption></figcaption></figure>
