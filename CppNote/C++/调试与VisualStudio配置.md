---
aliases:
  - debugging
  - 调试
  - breakpoint
  - visual studio settings
  - 断点
重要程度: 了解
未学: false
会看: false
会写: false
熟练: false
精通: true
---
调试（debug）是定位运行错误的关键，核心是**断点 + 单步 + 观察变量**。

- 在行号左侧点击设置**断点**（红点），运行到此处会暂停
- `F10` 逐过程（step over）、`F11` 逐语句（step into）
- “监视 / 局部变量”窗口实时查看变量值
- “调用堆栈”窗口查看函数调用链

Visual Studio 推荐设置：
- 把“解决方案配置”切到 **Debug**（含调试符号、不做优化）再调试
- 开启行号：选项 → 文本编辑器 → 所有语言 → 行号
- 快速打印调试可用 `std::cout` 或日志

```cpp
int main() {
    int sum = 0;
    for (int i = 1; i <= 3; ++i) {
        sum += i;     // 在此处打断点，观察 sum 的变化
    }
}
```
相关：[[C++编译链接流程]]
