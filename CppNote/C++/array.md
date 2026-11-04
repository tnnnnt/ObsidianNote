---
aliases:
  - "std::array"
  - "标准库数组"
重要程度: 一般
未学: true
会看: false
会写: false
熟练: false
精通: false
---
```cpp
#include <iostream>
#include <array>
int main() {
	std::array<int, 5> arr{};
	for(int i = 0; i < arr.size(); ++i) {
		arr[i] = 2;
	}
	return 0;
}
```
