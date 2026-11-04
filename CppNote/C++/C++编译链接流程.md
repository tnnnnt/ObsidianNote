---
aliases:
  - build process
  - 编译
  - 链接
  - compilation
  - linking
  - 预处理
重要程度: 一般
未学: false
会看: true
会写: false
熟练: false
精通: false
---
C++ 从源码到可执行文件经历几个阶段：

1. **预处理（Preprocessing）**：展开 `#include`、处理 `#define` / `#ifdef` 等，生成翻译单元（`.i`）
2. **编译（Compilation）**：把预处理后的代码翻译成汇编（`.s`），再汇编成目标文件 `.o` / `.obj`
3. **链接（Linking）**：把多个目标文件和库合并，解析 `Add` 等外部符号的地址，生成可执行文件

```cpp
// add.cpp
int Add(int a, int b) { return a + b; }

// main.cpp
int Add(int a, int b);     // 声明：告诉编译器这个符号存在
int main() {
    return Add(1, 2);      // 调用定义在另一翻译单元的函数
}
```

- 编译阶段各 `.cpp` 相互独立、互不可见
- 链接阶段才把“调用”和“定义”接起来
- 只声明未定义 → **链接错误**（undefined reference），区别于编译错误
- 声明放 [[C++头文件]]，多文件组织见 [[创建和使用库]]
