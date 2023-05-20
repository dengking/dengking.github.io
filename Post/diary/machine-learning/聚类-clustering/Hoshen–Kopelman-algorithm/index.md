# Hoshen–Kopelman algorithm



## wikipedia [Hoshen–Kopelman algorithm](https://en.wikipedia.org/wiki/Hoshen%E2%80%93Kopelman_algorithm) 

The **Hoshen–Kopelman algorithm** is a simple and efficient [algorithm](https://en.wikipedia.org/wiki/Algorithm) for labeling [clusters](https://en.wikipedia.org/wiki/Cluster_analysis) on a grid, where the grid is a regular [network](https://en.wikipedia.org/wiki/Artificial_neural_network) of cells, with the cells being either occupied or unoccupied. This algorithm is based on a well-known [union-finding algorithm](https://en.wikipedia.org/wiki/Disjoint-set_data_structure).

### Percolation theory

> NOTE:
>
> 一、渗透理论

[Percolation theory](https://en.wikipedia.org/wiki/Percolation_theory) is the study of the behavior and [statistics](https://en.wikipedia.org/wiki/Statistics) of [clusters](https://en.wikipedia.org/wiki/Cluster_analysis) on [lattices](https://en.wikipedia.org/wiki/Lattice_graph). Suppose we have a large square lattice where each cell can be occupied with the [probability](https://en.wikipedia.org/wiki/Probability) `p` and can be empty with the probability `1 – p`. Each group of neighboring occupied cells forms a **cluster**. Neighbors are defined as cells having a common side but not those sharing only a corner i.e. we consider the [4-connected neighborhood](https://en.wikipedia.org/wiki/Pixel_connectivity) that is top, bottom, left and right. Each occupied cell is independent of the status of its neighborhood. The number of clusters, the size of each cluster and their distribution are important topics in percolation theory.

### Hoshen–Kopelman algorithm for cluster finding

In this algorithm, we scan through a grid looking for occupied cells and labeling them with cluster labels. The scanning process is called a [raster scan](https://en.wikipedia.org/wiki/Raster_scan). The algorithm begins with scanning the grid cell by cell and checking whether the cell is occupied or not. If the cell is occupied, then it must be labeled with a **cluster label**. This **cluster label** is assigned based on the neighbors of that cell. (For this we are going to use [Union-Find Algorithm](https://en.wikipedia.org/wiki/Union-find_algorithm) which is explained in the next section.) If the cell doesn’t have any occupied neighbors, then a new label is assigned to the cell.

### Pseudocode

During the [raster scan](https://en.wikipedia.org/wiki/Raster_scan) of the grid, whenever an occupied cell is encountered, **neighboring cells** are scanned to check whether any of them have already been scanned. If we find already **scanned neighbors**, the `union` operation is performed, to specify that these neighboring cells are in fact members of the same equivalence class. Then the`find` operation is performed to find a representative member of that equivalence class with which the current cell will be labeled.

On the other hand, if the current cell has no neighbors, it is assigned a new, previously unused, label. The entire grid is processed in this way.

Following [pseudocode](https://en.wikipedia.org/wiki/Pseudocode) is referred from [Tobin Fricke's](https://www.ocf.berkeley.edu/~fricke/) implementation of the same algorithm.



## LeetCode

[LeetCode-130. Surrounded Regions-中等](https://leetcode.cn/problems/surrounded-regions/)