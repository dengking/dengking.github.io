# zhihu [手把手教你用傅立叶变换画可达鸭](https://zhuanlan.zhihu.com/p/72632360?utm_id=0)

## **离散傅立叶变换**





轮廓只是一些像素点围成的**多边形**。接下来我们要把轮廓转换成画笔的路径。

不过这个问题比看起来要困难不少。

- 孤岛

画笔从一个多边形跳转到另一个多边形，一定会留下多余的线条，影响效果。但有的跳转是必须的，比如可达鸭的眼睛和鼻子都是孤岛。

- 样本点的顺序

我们虽然知道样本点要从轮廓上取，但是每个轮廓从哪里开始？是顺时针还是逆时针？是画完一个多边形再画第二个，还是尽可能“一笔画”？

- 圆圈太多

傅里叶变换需要n个圆圈来拟合n个样本点。如果样本点取很多，虽然轮廓细节可以勾勒清晰，但是动画渲染会很慢。如何用尽可能少的圆圈勾勒出逼真的轮廓？



## 孤岛问题

画笔画出来的轨迹是连续的，也就是说画笔将所有样本点连成一块连通分量。要减少孤岛的违和感，需要用尽可能短的边将其连入联通分量中。

而最小生成树的[Kruskal](https://link.zhihu.com/?target=https%3A//en.wikipedia.org/wiki/Kruskal%27s_algorithm)算法也用了类似的思想。

用相似的贪心法，我们不难把孤岛连入整个轮廓。

## 样本点的顺序

理想情况下，不带重复的一笔画是最佳的画笔轨迹。一笔画问题就是寻找[欧拉路径](https://link.zhihu.com/?target=https%3A//zh.wikipedia.org/wiki/%E4%B8%80%E7%AC%94%E7%94%BB%E9%97%AE%E9%A2%98)。然而，只有2或0个点的度数为基数的连通图存在欧拉路径。连通图尚且不论，度数为3的点在可达鸭的轮廓中就有好多个，不可能存在欧拉路径。也就是说一笔画不适用于一般的图片。

退而求其次，如果我们允许画笔走回头路，同一条边画多次，那么是不是就有办法了呢？答案是肯定的。只要在连通图中做一次深度优先遍历（DFS)，遍历的顺序就可以看作是画笔的轨迹了。

然而怎么把轮廓变成连通图呢？

刚刚的[最小生成树](https://link.zhihu.com/?target=https%3A//en.wikipedia.org/wiki/Kruskal%27s_algorithm)给了我们一些新的启发。

如果我们把所有的轮廓上的每个像素点看作我们的样本点，那么它组成的最小生成树几乎肯定包含了大多数轮廓上的边，同时又把孤岛包含了进去，一箭双雕。

现在理论上我们已经能够用傅里叶变换画出可达鸭了。

**最小生成树的效率**

我们需要在一个完全图里找最小生成树，这恰巧是[Kruskal](https://link.zhihu.com/?target=https%3A//en.wikipedia.org/wiki/Kruskal%27s_algorithm)算法最不擅长的情况，复杂度基本上达到 �(�2����) 。可达鸭的轮廓有上万个点，用python算一次最小生成树可能需要几分钟。

好在二维平面欧氏距离的最小生成树有[更好的算法](https://link.zhihu.com/?target=https%3A//en.wikipedia.org/wiki/Euclidean_minimum_spanning_tree)，只需要 �(�����) 复杂度，我的电脑一秒以内就能算出来。大体的办法是先对点集做一个叫Delaunay的三角剖分，可以证明二位平面欧氏距离的最小生成树在这个三角剖分中。Delaunay需要 �(�����) ，三角剖分的边是 �(�) ，只对这些边跑[Kruskal](https://link.zhihu.com/?target=https%3A//en.wikipedia.org/wiki/Kruskal%27s_algorithm)就只用 �(�����) 了。

Delaunay在scipy里有现成实现。





## 圆圈太多

可达鸭的轮廓有上万个像素点组成，傅里叶变换后转换成上万个圆圈，效果并不理想。

要减少点的数量，最简单的方法就是取随机样本。

但是随机样本无法捕捉细节信息。当样本数量达到219的时候最小生成树画出的图已经有些难以辨认了。

![img](https://pic4.zhimg.com/80/v2-659d1683731db8aeba477ddb8316baa3_1440w.webp)

随机样本遇到了瓶颈，我们需要另想办法。

注意到可达鸭的轮廓有的地方平滑，细节少；有的地方曲折，细节多。

几乎是直线的地方信息含量少，只需要少量样本就能描绘，而细节丰富的地方需要更多的样本。有什么办法能按照这样的规律来调整我们的路径呢？

[Ramer–Douglas–Peucker算法](https://link.zhihu.com/?target=https%3A//en.wikipedia.org/wiki/Ramer%E2%80%93Douglas%E2%80%93Peucker_algorithm)就是为此就是为此设计。它能够简化几乎排一条直线上的样本点，只保留首尾；曲折较多的样本点则被更完整的保留。

【更新 07/16/2019】我原先使用了这个python的实现。

[fhirschmann/rdpgithub.com/fhirschmann/rdp![img](https://pic2.zhimg.com/v2-d613306a32b1f82456a81d1754badcf9_ipico.jpg)](https://link.zhihu.com/?target=https%3A//github.com/fhirschmann/rdp)

由于python的效率较低，我自己用cython重写了一个版本。

[biran0079/crdpgithub.com/biran0079/crdp![img](https://pic1.zhimg.com/v2-d23882456a47a9273248bf4969662d48_ipico.jpg)](https://link.zhihu.com/?target=https%3A//github.com/biran0079/crdp)

这样大多数图片不需要过度降取样，也能快速的计算路径。

```text
def rdp_downsample(path, epsilon):
    before_n = len(path)
    path = rdp(path, epsilon=epsilon)
    after_n = len(path)
    print(f'samples on path path after rdp: {before_n} -> {after_n}')
    return path
```

[Ramer–Douglas–Peucker](https://link.zhihu.com/?target=https%3A//en.wikipedia.org/wiki/Ramer%E2%80%93Douglas%E2%80%93Peucker_algorithm)可以将成千上万个点组成的路径减少1-2个数量级，同时不丢失太多轮廓细节。





# zhihu [鸭嘎嘎](https://www.zhihu.com/people/bi-ran-4)