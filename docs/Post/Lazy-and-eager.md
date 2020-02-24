# Lazy and eager

## Lazy 

### Lazy load

有的时候，如果一次性的将所有资源导入内存，如果资源较多，则可能导致整个过程耗时较长，这样做有如下弊端：

- 造成用户需要较长的等待时间
- 在开发过程中，有的时候只需要测试一个小的模块，压根就无需加载整个资源，这就造成了时间的浪费

如果能够load-on-need，即只在需要的时候才进行加载，则将一次性较长时间的加载分摊到了多次中，则整体的体验会更好一些，也更加节省时间一些。

#### Python lazy load module





### [Lazy evaluation](https://en.wikipedia.org/wiki/Lazy_evaluation)



#### Python generator

python generator是典型的lazy evaluation。

### Copy-on-write

参见维基百科[Copy-on-write](https://en.wikipedia.org/wiki/Copy-on-write)。

## Eager 

### Tensorflow eager 

