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
