---
aliases:
  - "自动类型推导"
  - "类型推导"
重要程度: 重要
未学: true
会看: false
会写: false
熟练: false
精通: false
---
`auto` 让编译器**根据初始化表达式自动推导变量类型**，C++11 引入（对应视频第 56 集）。

```cpp
auto x = 5;          // int
auto y = 3.14;       // double
auto s = std::string{"hi"};

std::vector<int> v = {1, 2, 3};
for (auto it = v.begin(); it != v.end(); ++it) { }   // 省去冗长迭代器类型
for (const auto& e : v) { }                          // 引用避免拷贝

auto Add(int a, int b) -> int { return a + b; }       // 拖尾返回类型（C++11）
// C++14 起连返回值也能推导：auto Add(int a,int b){ return a+b; }
```

- `auto` 必须有初始化（否则无法推导）
- 适合“类型名很长 / 不明显”处（迭代器、lambda）；基础类型显式写更清晰
- `const auto&` 读容器元素、`auto&&` 万能引用是常见惯用法
- `auto` 推导会退化（数组→指针、引用被剥除），必要时用 `decltype`
- 变量基础见 [[C++变量]]；与 [[lambda]]、[[模板]] 常配合使用
