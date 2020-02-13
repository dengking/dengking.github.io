# Architecture

## Library-base architecture

在阅读[Clang - Features and Goals](http://clang.llvm.org/features.html#libraryarch)时，其Library Based Architecture令我印象深刻，据我所知的，还有采用这种架构的有

- [nginx](https://nginx.org/en/docs/)
  [nginx](https://nginx.org/en/docs/)提供了非常多的Modules，这些Modules就是一个一个的library。
- [redis](https://redis.io/modules)
  [Redis Modules](https://redis.io/modules)，这些Modules就是一个一个的library。
- [Tuxedo (software)](https://en.wikipedia.org/wiki/Tuxedo_(software))

- [cpython](https://www.python.org/)也可以看做是library-base architecture，因为它允许Extending and Embedding the Python Interpreter[¶](https://docs.python.org/3/extending/index.html#extending-and-embedding-the-python-interpreter)
  参见：
  - [python bindings, how does it work?](https://stackoverflow.com/questions/10202306/python-bindings-how-does-it-work)
  - [dlopen](http://man7.org/linux/man-pages/man3/dlopen.3.html)


- operating system kernel

  大多数现代操作系统都支持[loadable kernel module](https://en.wikipedia.org/wiki/Loadable_kernel_module)特性

## Middleware

https://en.wikipedia.org/wiki/Middleware

### Message-oriented middleware

https://en.wikipedia.org/wiki/Message-oriented_middleware







## [Multitier architecture](https://en.wikipedia.org/wiki/Multitier_architecture) VS [Monolithic application](https://en.wikipedia.org/wiki/Monolithic_application)

TODO: 将在[The Structure of a Compiler](https://dengking.github.io/compiler-principle/Chapter-1-Introduction/1.2-The-Structure-of-a-Compiler/)中所总结的关于compiler的架构的内容添加到这里。

## Monolithic VS micro

[Monolithic Architecture and Microservices Concepts- Cloud Computing](https://www.howtechyy.com/2019/07/monolithic-architecture-vs-microservices-concepts.html)



[Microservices](https://en.wikipedia.org/wiki/Microservices)



[Monolithic kernel](https://en.wikipedia.org/wiki/Monolithic_kernel) vs [Microkernel](https://en.wikipedia.org/wiki/Microkernel)



