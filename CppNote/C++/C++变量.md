---
aliases:
  - variables
  - 变量
  - 基本类型
重要程度: 核心
未学: false
会看: false
会写: false
熟练: true
精通: false
---
变量是内存中一块**带名字、带类型**的存储。C++ 是静态类型语言，声明时必须确定类型。

```cpp
int age = 25;            // 整型
double price = 9.99;    // 双精度浮点
char grade = 'A';       // 字符
bool isOpen = true;     // 布尔
unsigned int u = 0;     // 无符号整型（仅非负）

// C++11 起推荐花括号初始化，能防止窄化转换
int x{5};
int y{};                // 值初始化为 0
```

- 内建（基本）类型：`bool` `char` `int` `float` `double` 及带 `short/long/unsigned` 修饰的变体
- `sizeof(int)` 查看类型占用字节数（与平台相关）
- 需要一块连续同类型存储时用 [[数组]]；想间接访问内存用 [[指针]]
- 函数里声明变量见 [[C++函数]]
