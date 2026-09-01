```cpp
#include <iostream>
class Entity {
};
int main() {
	int* a = new int; // 定义一个指针变量 a，指向一个动态分配的整数
	int* b = new int(10);// 定义一个指针变量 b，指向一个动态分配的整数，并初始化为 10
	int* c = new int[10]; // 定义一个指针变量 c，指向一个动态分配的整数数组，大小为 10
	Entity* d = new Entity; // 定义一个指针变量 d，指向一个动态分配的 Entity 对象
	Entity* e = new Entity(); // 定义一个指针变量 e，指向一个动态分配的 Entity 对象，并调用默认构造函数
	Entity* f = new Entity[10]; // 定义一个指针变量 f，指向一个动态分配的 Entity 对象数组，大小为 10

	// 与使用new等价的操作，区别仅在于使用malloc分配内存时不会调用构造函数，而使用new分配内存时会调用构造函数（不建议使用malloc分配对象内存，建议使用new分配对象内存）
	//Entity* g = (Entity*)malloc(sizeof(Entity)); // 定义一个指针变量 g，指向一个动态分配的 Entity 对象，使用 malloc 分配内存

	// 记得释放内存，避免内存泄漏
	delete a; // 释放动态分配的整数
	delete[] c; // 释放动态分配的整数数组

	// 与delete等价的操作，区别仅在于使用free释放内存时不会调用析构函数，而使用delete释放内存时会调用析构函数（不建议使用free释放对象内存，建议使用delete释放对象内存）
	//free(g); // 释放动态分配的 Entity 对象，使用 free 释放内存

	Entity* h = new(b) Entity; // 定义一个指针变量 h，指向一个动态分配的 Entity 对象，使用 placement new 在 b 指向的内存上构造对象
	return 0;
}
```
new是运算符，也是关键字
[[placement new]]
