两种使用方式
1. 在类外部使用static，链接只在内部，意味着只能对定义它的翻译单元可见
```cpp
// A.cpp
static int s_Variable = 5;
// B.cpp
#include <iostream>
int s_Variable = 10;
int main() {
	std::cout << "Static variable: " << s_Variable << std::endl;
	return 0;
}
```
运行结果是10，因为A.cpp中的s_Variable是static的，对B.cpp不可见，如果把static去掉则会链接错误，因为s_Variable被定义了2次，可以修改为如下所示
```cpp
// A.cpp
int s_Variable = 5;
// B.cpp
#include <iostream>
extern int s_Variable;
int main() {
	std::cout << "Static variable: " << s_Variable << std::endl;
	return 0;
}
```
[[extern]]用于声明变量，注意如果[[extern]]后紧接着赋值则为声明并定义变量
```cpp
#include <iostream>
static void fff() {
	static int x = 0;
	++x;
	std::cout << x << std::endl;
}
int main() {
	fff();
	fff();
	fff();
	fff();
	return 0;
}
```
2. 在类内部使用static，意味着它实际上将与类的所有实例共享内存
```cpp
#include <iostream>
class Entity {
public:
	static int x, y;
	static void print() {
		std::cout << x << ", " << y << std::endl;
	}
};
int Entity::x = 0; // 必须在类外初始化静态成员变量
int Entity::y = 0; // 必须在类外初始化静态成员变量
int main() {
	Entity::x = 2;
	Entity::y = 3;
	Entity::print();
	return 0;
}
```

利用static设计[[单例]]类
```cpp
#include <iostream>
class Singleton {
public:
	static Singleton& getInstance() {
		// 这里如果没有static，则会在栈上创建一个对象
		// 每次调用getInstance()都会创建一个新的对象
		// 而static则保证了只会创建一次
		static Singleton instance;
		return instance;
	}
	void fff(){}
};
int main() {
	Singleton::getInstance().fff();
	return 0;
}
```
注意事项：
1. 静态方法不能访问非静态变量
2. 类中的常量表达式必须是静态的
```cpp
#include <iostream>
class Entity
{
public:
	static constexpr int value = 10;
};
```
