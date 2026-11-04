---
aliases:
  - "当前对象"
  - "this指针"
重要程度: 重要
未学: true
会看: false
会写: false
熟练: false
精通: false
---
```cpp
class Entity {
public:
	int a;
	double b;
	Entity() : a(0), b(0.0) {}
	Entity(int a, double b) {
		this->a = a;
		this->b = b;
	}
};
```
