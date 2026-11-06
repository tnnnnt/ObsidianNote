---
aliases:
  - 类
重要程度: 核心
未学: false
会看: false
会写: false
熟练: true
精通: false
---
```cpp
#include<iostream>
class Player {
public:
	int x;
	int y;
	int speed;
	void Move(int xa, int ya) {
		x += xa * speed;
		y += ya * speed;
	}
};
int main() {
	Player player;
	player.Move(1, 1);
	return 0;
}
```
