---
aliases:
  - header files
  - 头文件
  - include
重要程度: 重要
未学: false
会看: false
会写: false
熟练: true
精通: false
---
头文件（`.h` / `.hpp`）用于**声明**接口（函数、类、常量），让其他 `.cpp` 在编译前知道符号长什么样。

```cpp
// math.h
#pragma once                 // 头文件守卫：防止同一头文件被重复包含
int Add(int a, int b);       // 仅声明

// 传统写法（无 #pragma once 时）：
// #ifndef MATH_H
// #define MATH_H
// int Add(int a, int b);
// #endif
```

```cpp
// main.cpp
#include "math.h"            // 双引号：先查当前目录，再查系统目录
#include <iostream>          // 尖括号：查系统 / 标准库目录
int main() { std::cout << Add(1, 2); }
```

- `#include` 在预处理阶段把头文件内容“复制粘贴”进来
- 重复包含会因多重定义报错，故需要头文件守卫（`#pragma once` 最简便）
- 这是分离编译的基础，详见 [[C++编译链接流程]] 与 [[宏]]
