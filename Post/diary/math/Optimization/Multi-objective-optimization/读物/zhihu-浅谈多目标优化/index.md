# zhihu [浅谈多目标优化](https://zhuanlan.zhihu.com/p/158705342)

## 概念

**单目标优化**的情况下，只有一个目标，任何两解都可以依据单一目标比较其好坏，可以得出没有争议的**最优解**。

**多目标化**与传统的**单目标优化**相对。**多目标优化**的概念是在某个情景中在需要达到多个目标时，由于容易存在目标间的**内在冲突**，一个目标的**优化**是以其他目标**劣化**为代价，因此很难出现**唯一最优解**，取而代之的是在他们中间做出协调和折衷处理，使总体的目标尽可能的达到最优。





## Part 2.1 常用解法模型

### i) 线性加权

线性加权是多目标优化广泛使用的一种模型．SAW(Simple Additive Weighting)是其中经典的一类线性加权求和方法．它忽略不同目标函数有不同的单位和范围，通过给不同的目标函 数制定相应的权重，将所有的目标函数进行线性加权，用一个综合的效用函数来代表总体优化的目标．最优的效用函数对应的解即被认为是问题的最优解，从而将多目标优化问题转化成单目标优化问题．对于第i个目标函数f (x)，用W 表示它的权重，那么多目标优化模型可以转化成下图公式。