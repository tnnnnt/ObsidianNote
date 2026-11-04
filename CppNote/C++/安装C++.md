---
aliases:
  - install
  - 环境搭建
  - setup
重要程度: 了解
未学: false
会看: true
会写: false
熟练: false
精通: false
---
各平台安装 C++ 编译器 / IDE：

```bash
# Windows：安装 Visual Studio，勾选“使用 C++ 的桌面开发”（自带 MSVC）
# 或安装 MinGW-w64，搭配 VS Code 使用

# macOS：安装 Xcode 命令行工具（自带 Clang）
xcode-select --install

# Linux (Ubuntu/Debian)：安装 GNU 编译器集合
sudo apt install g++
```

验证安装（终端执行）：
```bash
g++ --version     # 或 clang++ --version / cl
```

编译并运行一个源文件：
```bash
g++ main.cpp -o main && ./main
```
- Windows 常用 **MSVC**（Visual Studio 自带）
- macOS 默认 **Clang**
- Linux 常用 **G++（GCC）**

编译背后发生了什么见 [[C++编译链接流程]]。
