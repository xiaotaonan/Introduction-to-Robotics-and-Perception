# 3.5.8. 计算值函数

> 对于任何固定策略，我们都可以精确计算 value 函数。

我们可以通过求解线性方程组来计算 的$$\mathcal{Z}^{\pi}$$精确值。回想一下我们对 value 函数的递归定义：

$$
\begin{equation}
V^\pi(x) = \bar{R}(x,\pi(x)) + \gamma \sum_{x'} P(x'|x, \pi(x)) V^\pi(x')
\end{equation}
$$

这个方程式适用于状态的每个可能值$$x$$。因此，如果存在$$n$$可能的状态，我们就会得到$$n$$未知数中的$$n$$线性方程。这些$$n$$方程中的每一个都是通过计算$$\mathcal{V}^{\pi}(x)$$的特定\
值$$x$$而得到的。收集左侧的未知$$\mathcal{V}^{\pi}$$项和右侧的已知$$\overline{R}(x,\pi(x))$$项，我们得到

$$
\begin{equation}
V^\pi(x) - \gamma \sum_{x'} P(x'|x, \pi(x)) V^\pi(x') = \bar{R}(x,\pi(x)).
\end{equation}
$$

为了使我们的扫地机器人示例清晰而简洁，让我们将标量$$T_{xy}^{\pi} \approx P(y|x,\pi(x))$$定义为策略下从状态$$x$$到状态$$y$$的转换概率$$\pi$$。此外，我们使用缩写 L、K、O、H 和 D 来表示房间，并使用 policy $$\pi$$\
下 state $$x$$的值的简写$$\mathcal{V}_x^{\pi} \approx \mathcal{V}^{\pi}(x)$$。使用这种表示法，我们可以计算上面的表达式。对于$$x=L$$，我们得到

$$
\begin{equation}
V^\pi_L - \gamma \sum_{x'\in {L,K,O,H,D}} T^\pi_{Lx'} V^\pi_{x'} = \bar{R}(L,\pi(L))
\end{equation}
$$

或者，经过一些代数之后：

$$
\begin{equation}
(1 - \gamma T^\pi_{LL}) V^\pi_{L}
- \gamma T^\pi_{LK} V^\pi_{K} 
- \gamma T^\pi_{LO} V^\pi_{O} 
- \gamma T^\pi_{LH} V^\pi_{H} 
- \gamma T^\pi_{LD} V^\pi_{D} 
= \bar{R}(L,\pi(L))
\end{equation}
$$

如果我们对 5 个 Rooms 中的每一个应用相同的过程，我们将得到以下 5 个方程：

$$
\begin{equation}
\begin{aligned}
(1 - \gamma T^\pi_{LL}) V^\pi_{L}
- \gamma T^\pi_{LK} V^\pi_{K} 
- \gamma T^\pi_{LO} V^\pi_{O} 
- \gamma T^\pi_{LH} V^\pi_{H} 
- \gamma T^\pi_{LD} V^\pi_{D} 
&= \bar{R}(L,\pi(L))
\\
- \gamma T^\pi_{KL} V^\pi_{L}
+ (1 - \gamma T^\pi_{KK}) V^\pi_{K} 
- \gamma T^\pi_{KO} V^\pi_{O} 
- \gamma T^\pi_{KH} V^\pi_{H} 
- \gamma T^\pi_{KD} V^\pi_{D} 
&= \bar{R}(K,\pi(K))
\\
- \gamma T^\pi_{OL} V^\pi_{L}
- \gamma T^\pi_{OK} V^\pi_{K} 
+ (1 - \gamma T^\pi_{OO}) V^\pi_{O} 
- \gamma T^\pi_{OH} V^\pi_{H} 
- \gamma T^\pi_{OD} V^\pi_{D} 
&= \bar{R}(O,\pi(O))
\\
- \gamma T^\pi_{HL} V^\pi_{L}
- \gamma T^\pi_{HK} V^\pi_{K} 
- \gamma T^\pi_{HO} V^\pi_{O} 
+ (1 - \gamma T^\pi_{HH}) V^\pi_{H} 
- \gamma T^\pi_{HD} V^\pi_{D} 
&= \bar{R}(H,\pi(H))
\\
- \gamma T^\pi_{DL} V^\pi_{L}
- \gamma T^\pi_{DK} V^\pi_{K} 
- \gamma T^\pi_{DO} V^\pi_{O} 
- \gamma T^\pi_{DH} V^\pi_{H} 
+ (1 - \gamma T^\pi_{DD}) V^\pi_{D} 
&= \bar{R}(D,\pi(D))
\end{aligned}
\end{equation}
$$

这些方程中的未知数是$$\mathcal{V}_L^{\pi},\mathcal{V}_K^{\pi},\mathcal{V}_O^{\pi},\mathcal{V}_H^{\pi},\mathcal{V}_D^{\pi}$$。所有其他项要么是 transitionprobabilities 要么是 expected rewards，其值要么是给定的，要么可以很容易地计算。

在代码中，这将变为：

```python
def calculate_value_system(pi, gamma=0.9):
    """Calculate A, b matrix of linear system for value computation."""
    b = np.empty((5,), float)
    AA = np.empty((5,5), float)
    for x, room in enumerate(vacuum.rooms):
        a = pi[x] # action under policy
        b[x] = T[x,a] @ R[x,a] # expected reward under policy pi
        AA[x] = -gamma * T[x,a]
        AA[x,x] += 1
    return AA,b

def calculate_value_function(pi, gamma=0.9):
    """Calculate value function for given policy"""
    AA, b = calculate_value_system(pi, gamma)
    return np.linalg.solve(AA,b)
```

这是策略 `reasonable_policy` 的 linearsystem（实际上几乎总是错误的）：

```python
AA, b = calculate_value_system(reasonable_policy)
print(f"A =\n{AA}")
print(f"b = {b}")
```

```
A =
[[ 0.1  -0.   -0.   -0.   -0.  ]
 [-0.72  0.82 -0.   -0.   -0.  ]
 [-0.   -0.    0.82 -0.72 -0.  ]
 [-0.72 -0.   -0.    0.82 -0.  ]
 [-0.   -0.   -0.   -0.72  0.82]]
b = [10.  8.  0.  8.  0.]
```

当我们在策略 `reasonable_policy` 下计算 value 函数 $$\mathcal{V}^{\pi}$$ 时，我们看到我们的精确 value 函数与上面的 Monte Carlo 估计值很好地近似：

```python
value_for_pi = calculate_value_function(reasonable_policy)
print("V(reasonable_policy):")
for i,room in enumerate(vacuum.rooms):
    print(f"  {room:12}: {value_for_pi[i]:.2f}")
```

```
V(reasonable_policy):
  Living Room : 100.00
  Kitchen     : 97.56
  Office      : 85.66
  Hallway     : 97.56
  Dining Room : 85.66
```
