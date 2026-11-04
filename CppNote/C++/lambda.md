---
aliases:
  - "匿名函数"
  - "Lambda表达式"
重要程度: 重要
未学: true
会看: false
会写: false
熟练: false
精通: false
---
>\[捕获](参数){函数体}

1. 捕获
可以有0个或多个，用逗号分隔
* =是所有变量值传递
* &是所有变量引用传递
* a是变量a值传递
* &a是变量a引用传递
* this是当前对象传递
当使用了捕获，则不能使用原始函数指针作为参数，而应该使用std::function
```cpp
#include <iostream>
#include <vector>
#include <functional>
static void ForEach(const std::vector<int>& vec, const std::function<void(int)>& func) {
	for (int value : vec) {
		func(value);
	}
}
int main() {
	std::vector<int> vec = { 1, 2, 3, 4, 5 };
	int a = 5;
	ForEach(vec, [a](int value) {
		std::cout << "Value: " << a << std::endl;
		});
	return 0;
}
```

2. 修饰符[[mutable]]
