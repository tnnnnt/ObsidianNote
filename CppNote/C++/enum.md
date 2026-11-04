---
aliases:
  - "枚举"
重要程度: 一般
未学: true
会看: false
会写: false
熟练: false
精通: false
---
基本使用方法
```cpp
#include <iostream>
enum Number {
	Zero,// 0
	One,// 1
	Three = 3,// 3
	Four// 4
};
int main() {
	Number n = One;
	if (n == 1) {
		std::cout << "n is One" << std::endl;
	}
	if (n == Three) {
		std::cout << "n is Three" << std::endl;
	}
	return 0;
}
```
指定想要给枚举赋值的**整数**类型，注意必须是整数类型
```cpp
enum Number:unsigned char {
	Zero,// 0
	One,// 1
	Three = 3,// 3
	Four// 4
};
```
[[枚举类]]
