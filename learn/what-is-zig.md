# 什么是 Zig

根据其官网所述：

> Zig 是一种通用的编程语言和工具链，用于维护健壮、最优和可重用的软件

这样的概念解释可能比较模糊，我们来看看维基百科怎么说的：

> Zig 是一种命令式、通用、静态类型、编译的系统编程语言，由 Andrew Kelley 设计。
> 它旨在替代C编程语言，其目标是更小，编程更简单，同时还提供现代功能，新的优化和各种安全机制，
> 同时不像其他语言那样对运行时安全性的要求。

> 语言简单性的改进与流控制、函数调用、库导入、变量声明和 Unicode 支持有关。
> 此外，该语言不使用宏或预处理器指令。从现代语言中采用的功能包括添加编译时泛型类型，
> 允许函数处理各种数据，以及一小组新的编译器指令，以允许使用反射访问有关这些类型的信息。
> Zig 还旨在提高代码的安全性，它不提供垃圾回收（GC），但是使用可选类型代替 `null` ，这避免了空指针的出现。

## 为何使用 Zig

从本质上看，Zig是一门 `low level` 的高级语言，它和C很像，但改善旧问题并提供了完善的工具链，并且它可选支持 `libc`

一切都是强制显示声明式，这使得代码阅读很轻松！

如果你是嵌入式开发，亦或者对速度有很高的要求，还不想使用心智负担太高的其他高级语言，或许 Zig 很适合你。

## 特点

- 无隐式执行
- 手动内存控制，精确的内存泄漏跟踪
- 完善的堆栈跟踪（在裸机器上也可以）
- 对交叉编译的一流支持
- 标准库集成 libc ，但不依赖它
- 类型作为一等公民
- 可选类型代替 `null`，详见[计算机科学中最严重的错误](https://www.lucidchart.com/techblog/2015/08/31/the-worst-mistake-of-computer-science/)
- 编译期执行实现泛型和反射
- 无需 FFI/bindings 的 C 库集成
- 非常强大的构建系统

有几点是非常值得单独拿出来说明一下的：

_Zig 会要求你显示传递和管理你的内存，并且编译时就会跟踪你的内存是否发生泄漏，
高明的可选类型（这和rust的option有异曲同工之妙），强大的编译期运行，你可实现很多花哨的操作，而构建系统则被很多 C 项目拿去作为工具链使用_

## 了解更多 ？

你可以查看[这里](about/well-known-lib.html)，列出了一些仍在活跃状态较为著名的 zig 库或者实现