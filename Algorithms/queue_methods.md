# აღწერეთ რიგის რამდენიმე მეთოდი. მოიყვანეთ მაგალითები.

1. **push()**: ამატებს ელემენტს რიგის ბოლოში

```cpp
#include <iostream>
#include <queue>

int main() {
    std::queue<int> myQueue;

    myQueue.push(10);
    myQueue.push(20);
    myQueue.push(30);

    return 0;
}
```

2. **pop()**: შლის ელემენტს რიგის თავიდან

```cpp
#include <iostream>
#include <queue>

int main() {
    std::queue<int> myQueue;

    myQueue.push(10);
    myQueue.push(20);
    myQueue.push(30);

    myQueue.pop();

    return 0;
}
```

3. **front()**: აბრუნებს რეფერენსს რიგის პირველ ელემენტეზე

```cpp
#include <iostream>
#include <queue>

int main() {
    std::queue<int> myQueue;

    myQueue.push(10);
    myQueue.push(20);
    myQueue.push(30);

    std::cout << "Front element: " << myQueue.front() << '\n';

    return 0;
}

```

4. **back()**: აბრუნებს რეფერენსს რიგის ბოლო ელემენტზე

```cpp
#include <iostream>
#include <queue>

int main() {
    std::queue<int> myQueue;

    myQueue.push(10);
    myQueue.push(20);
    myQueue.push(30);

    std::cout << "Back element: " << myQueue.back() << '\n'; // Output: 30

    return 0;
}
```

5. **empty()**:

```cpp
#include <iostream>
#include <queue>

int main() {
    std::queue<int> myQueue;

    std::cout << "Is queue empty? " << (myQueue.empty() ? "Yes" : "No") << std::endl; // Output: Yes
    myQueue.push(10);
    std::cout << "Is queue empty? " << (myQueue.empty() ? "Yes" : "No") << std::endl; // Output: No

    return 0;
}

```
