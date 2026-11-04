---
aliases:
  - C++简介
  - 简介
  - introduction
重要程度: 了解
未学: false
会看: false
会写: false
熟练: false
精通: true
---
C++ 是一种**编译型、静态类型、多范式**的编程语言，由 Bjarne Stroustrup 在 C 语言基础上扩展而来，支持面向对象、泛型与过程式编程。

一个最小的 C++ 程序：
```cpp
#include <iostream>
int main() {
    std::cout << "Hello, C++!" << std::endl;
    return 0;
}
```
- `#include <iostream>`：引入标准输入输出流库
- `main`：程序入口函数，返回 `int` 表示退出码
- `std::cout`：标准输出流，`<<` 把内容推入流中

推荐学习路径：先把「变量 / 函数 / 控制流 / 指针 / 引用」等基础打牢，再进入类与对象。
[[C++编译链接流程]] · [[C++函数]] · [[C++变量]]
