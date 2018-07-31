### 衡量模型的好与坏需要考虑两点
1. 模型的复杂度(complexity)；这点衡量了模型的能力大小，比如二次函数空间包含线性函数空间，因此前者能力大，后者能力小。
2. 针对于目前要解决的问题，选择复杂度合适的模型。复杂度太小，造成训练后的模型偏差大；复杂度太大，造成训练后的模型方差大。

假设我们要解决某个回归问题，该问题的真实解为 $$Y = f(X) + \epsilon $$ 其中 $f(x)$为最佳解，$\epsilon$为不可约误差(irreducible error)。
我们以 $D_1, D_2, .., D_M$ 表示M个训练集(假设每个训练集中包含N个训练样本)，它们彼此独立；以(x, y)表示独立的测试集；以F表示我们的模型，$F_1, F_2, .., F_M$ 分别表示在M个训练集上
各自训练后的模型；

$$bias(F) = \frac{1}{M} \sum_i (y - F_i(x))$$

$$variance(F) = \frac{1}{M} \sum_i (F_i(x) - \barF(x))^2 $$
* 偏差(bias)衡量了模型能否胜任要解决问题的能力
* 方差(variance)衡量了模型在要解决问题上的稳定性


---
参考
[1] http://scott.fortmann-roe.com/docs/BiasVariance.html
[2] https://www.jianshu.com/p/005a4e6ac775
[3] https://web.stanford.edu/~hastie/Papers/ESLII.pdf
