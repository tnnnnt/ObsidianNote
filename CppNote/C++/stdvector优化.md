---
aliases:
  - "vector optimization"
  - "vector优化"
  - "std::vector"
重要程度: 重要
未学: true
会看: false
会写: false
熟练: false
精通: false
---
`std::vector` 是动态数组，理解其扩容机制能避开性能陷阱（对应视频第 48 集）。

```cpp
#include <vector>
std::vector<int> v;
v.reserve(100);            // 预分配容量，避免反复重新分配
for (int i = 0; i < 100; ++i)
    v.push_back(i);        // 容量足够时不会重新分配

v.emplace_back(123);       // 在容器内直接构造，少一次拷贝

v.shrink_to_fit();         // 删除元素后释放多余容量
```

- `size()` 是元素个数，`capacity()` 是不扩容能容纳的个数
- 容量不足时 vector 会**重新分配**（通常翻倍）并搬移旧元素，开销大
- 已知规模时先 `reserve`；优先 `emplace_back` 而非 `push_back`
- 遍历用 `for (const auto& x : v)` 避免拷贝
- 动态数组基础见 [[动态数组]]、[[数组]]；泛型见 [[模板]]
