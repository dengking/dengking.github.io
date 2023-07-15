# Thoughts

- 结构：产生式是containing关系，是树结构；函数是computation graph
- 不同类型的graph支持不同的操作，但是有一些基本操作是全部都要支持的，比如查询一个node的adjacent node
- 图，排序，关系，有序性，方向



简单仅仅是复杂的一种简化，比如：chain《-tree《-graph；



## divide-and-conquer-and-recursion



一分为几个(divide)，then recursion(conquer)，这是divide-and-conquer-and-recursion的常用模式

1、binary-search其实是一种deep-first-search

一等分为二，因此不需要考虑balanced的问题

2、quick-sort: 根据pivot一分为二-then recursion，它需要考虑balanced问题，因为它无法保证严格的等分

3、segment-tree将segment一等分为二，segment tree是dfs recursion的最最典型的模版

一等分为二，因此不需要考虑balanced的问题

4、[Ramer–Douglas–Peucker algorithm](https://en.wikipedia.org/wiki/Ramer%E2%80%93Douglas%E2%80%93Peucker_algorithm)



## Disjoint-set & connected-component

stackoverflow [Can we detect cycles in directed graph using Union-Find data structure?](https://stackoverflow.com/questions/61167751/can-we-detect-cycles-in-directed-graph-using-union-find-data-structure)

stackoverflow [Disjoint Set Union with directed graph](https://stackoverflow.com/questions/71028191/disjoint-set-union-with-directed-graph)



### Disjoint-set 取出 connected-component 的方式

1、hash map

2、double connected linked list

