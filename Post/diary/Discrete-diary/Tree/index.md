# Tree diary

zhihu [你认为最优美的数据结构是什么？ - 任路遥的回答 - 知乎](https://www.zhihu.com/question/32163076/answer/57422562) 

> 私以为，数据结构很大部分离不开树的思想，容我挂一漏万。
>
> 无论是DSU（[并查集](https://www.zhihu.com/search?q=并查集&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra={"sourceType"%3A"answer"%2C"sourceId"%3A57422562})），Heap（堆），BIT（[树状数组](https://www.zhihu.com/search?q=树状数组&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra={"sourceType"%3A"answer"%2C"sourceId"%3A57422562})），SegmentTree（[线段树](https://www.zhihu.com/search?q=线段树&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra={"sourceType"%3A"answer"%2C"sourceId"%3A57422562})），四分树，字母树，AC自动机，后缀大家族（SA[后缀数组](https://www.zhihu.com/search?q=后缀数组&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra={"sourceType"%3A"answer"%2C"sourceId"%3A57422562})，SAM后缀自动机，ST[后缀树](https://www.zhihu.com/search?q=后缀树&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra={"sourceType"%3A"answer"%2C"sourceId"%3A57422562})），[二叉搜索树](https://www.zhihu.com/search?q=二叉搜索树&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra={"sourceType"%3A"answer"%2C"sourceId"%3A57422562})，[平衡树](https://www.zhihu.com/search?q=平衡树&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra={"sourceType"%3A"answer"%2C"sourceId"%3A57422562})大家族（AVL，[红黑树](https://www.zhihu.com/search?q=红黑树&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra={"sourceType"%3A"answer"%2C"sourceId"%3A57422562})，Treap，Splay，SBT，替罪羊树），[kd-tree](https://www.zhihu.com/search?q=kd-tree&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra={"sourceType"%3A"answer"%2C"sourceId"%3A57422562})，PQ-tree,B树等等都离不开树的思想。上面提到的每个，我想每个OIer或多或少都能讲出许多道道。
>
> 
>
> 作者：任路遥
> 链接：https://www.zhihu.com/question/32163076/answer/57422562
> 来源：知乎
> 著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。



## 如何得到二叉树的last-internal-node

这是我在阅读 geeksforgeeks [Building Heap from Array](https://www.geeksforgeeks.org/building-heap-from-array/) 时，其中提到的:

> **Last non-leaf node** *= parent of last-node.*



## implicit data structure tree

heap、bit、union-find-set等都是将tree存储于array中，这是因为这些tree都是complete、perfect的



## children、parent

我们寻常使用的tree的node保存的是child pointer，通过一个node可以获得它们的children node，但是有一些特殊的tree，它们则不同:

1、union-find set: parent node、botom-up

2、heap

3、Binary Indexed Tree or Fenwick Tree，和heap类似，通过数学运算能够准确计算得到parent、children





child pointer:  children contain、top-down、stop condition: Leaf node

parent pointer: bottom-up、stop condition: root node
