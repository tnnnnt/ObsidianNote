---
aliases:
  - "functions"
  - "函数"
  - "function"
重要程度: 核心
未学: true
会看: false
会写: false
熟练: false
精通: false
---
函数是可复用的代码块，由返回类型、名称、参数列表、函数体组成。

```cpp
int Multiply(int a, int b);          // 声明（通常放头文件）

int Multiply(int a, int b) {         // 定义
    return a * b;
}

int Multiply(int a, int b, int c) {  // 函数重载：同名不同参数
    return a * b * c;
}

int main() {
    int r = Multiply(3, 4);          // r = 12
}
```

- 可“提前声明、延后定义”：声明给编译器签名，定义给实现
- 函数重载（overload）靠**参数类型/个数**区分，返回类型不算
- 参数默认按值传递（拷贝）；想改外部变量用 [[引用]] 或 [[指针]]
- 指向函数的指针见 [[函数指针]]；声明规范见 [[C++头文件]]
