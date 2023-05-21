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

During the [raster scan](https://en.wikipedia.org/wiki/Raster_scan) of the grid, whenever an occupied cell is encountered, **neighboring cells** are scanned to check whether any of them have already been scanned. If we find already **scanned neighbors**, the `union` operation is performed, to specify that these neighboring cells are in fact members of the same **equivalence class**. Then the`find` operation is performed to find a **representative member** of that equivalence class with which the current cell will be labeled.

On the other hand, if the current cell has no neighbors, it is assigned a new, previously unused, label. The entire grid is processed in this way.

Following [pseudocode](https://en.wikipedia.org/wiki/Pseudocode) is referred from [Tobin Fricke's](https://www.ocf.berkeley.edu/~fricke/) implementation of the same algorithm.



```pseudocode
Raster Scan and Labeling on the Grid
largest_label = 0;
label = zeros[n_columns, n_rows]
labels = [0:n_columns*n_rows] /* Array containing integers from 0 to the size of the image. */

for x in 0 to n_columns {
    for y in 0 to n_rows {
        if occupied[x, y] then
            left = label[x-1, y];
            above = label[x, y-1];
            if (left == 0) and (above == 0) then /* Neither a label above nor to the left. */
                largest_label = largest_label + 1; /* Make a new, as-yet-unused cluster label. */
                label[x, y] = largest_label;
            else if (left != 0) and (above == 0) then /* One neighbor, to the left. */
                label[x, y] = find(left);
            else if (left == 0) and (above != 0) then /* One neighbor, above. */
                label[x, y] = find(above);
            else /* Neighbors BOTH to the left and above. */
                union(left,above); /* Link the left and above clusters. */
                label[x, y] = find(left);
    }
}

Union
void union(int x, int y) {
    labels[find(x)] = find(y);
}

Find
int find(int x) {
    int y = x;

    while (labels[y] != y)
        y = labels[y];

    while (labels[x] != x)  {
        int z = labels[x];
        labels[x] = y;
        x = z;
    }

    return y;
}
```

> NOTE:
>
> 一、left 和 above是之前已经访问过的

## LeetCode

[LeetCode-130. Surrounded Regions-中等](https://leetcode.cn/problems/surrounded-regions/)