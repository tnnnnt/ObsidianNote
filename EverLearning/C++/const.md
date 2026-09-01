```cpp
#include <iostream>
class Entity {
private:
	int m_X;
	int* m_Y;
	mutable int m_Z; // mutable成员变量，可以在const成员函数中修改
public:
	int GetX() const { // const成员函数，不能修改成员变量
		m_Z = 10; // 可以修改mutable成员变量
		return m_X;
	}
	const int* const GetY() const { return m_Y; } // const成员函数，返回指向常量的指针
};
int main() {
	//const的使用
	const int a = 10; // 定义一个常量a，值为10
	const int* p = &a; // 定义一个指向常量的指针p，指向a
	int const* q = &a; // 定义一个指向常量的指针q，指向a
	int b = 20;
	int* const r = &b; // 定义一个常量指针r，指向b
	const int* const s = &a; // 定义一个指向常量的常量指针s，指向a
}
```
[[constexpr]]
[[mutable]]
