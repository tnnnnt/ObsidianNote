```cpp
#include <iostream>
class Entity {
private:
	int m_X;
	mutable int m_DebugCount = 0; // mutable成员变量，可以在const成员函数中修改
public:
	int GetX() const { // const成员函数，不能修改成员变量
		++m_DebugCount; // 可以修改mutable成员变量
		return m_X;
	}
};
int main() {
	int x = 8;
	auto f = [x]() mutable { // lambda表达式，捕获x，mutable允许修改捕获的变量
		++x; // 修改捕获的变量
		std::cout << x << std::endl; // 输出修改后的值
		};
	f(); // 调用lambda表达式
	// 输出x的值，仍然是8，因为lambda表达式捕获的是x的副本
}
```
[[const]]
[[lambda]]
