# აღწერეთ პრიორიტეტების რიგის რამდენიმე მეთოდი. მოიყვანეთ მაგალითები.

1. **push()**: ამატებს ახალ ელემენტს პრიორიტეტების რიგში. ჩამატების შემდეგ
   პრიორიტეტების რიგში ელემენტების გადალაგება ხდება რათა გროვის პრინციპი დაცული
   იყოს.

```cpp
#include <iostream>
#include <queue>

int main() {
    std::priority_queue<int> pq;
    pq.push(30);
    pq.push(10);
    pq.push(50);

    std::cout << "Priority Queue after pushing elements: ";
    while (!pq.empty()) {
        std::cout << pq.top() << " ";
        pq.pop();
    }
    std::cout << '\n';

    return 0;
}
```

2. **`top()`**: ეს მეთოდი აბრუნებს რეფერენსს ყველაზე პრიორიტეტულ ელემენტებს

```cpp
#include <iostream>
#include <queue>

int main() {
    std::priority_queue<int> pq;
    pq.push(30);
    pq.push(10);
    pq.push(50);

    std::cout << "Top element of the Priority Queue: " << pq.top() << '\n';

    return 0;
}
```

3. **`pop()`**: ეს მეთოდი ყველაზე მაღალი პრიორიტეტულობის ელემენტს შლის რიგიდან

```cpp
#include <iostream>
#include <queue>

int main() {
    std::priority_queue<int> pq;
    pq.push(30);
    pq.push(10);
    pq.push(50);

    std::cout << "Priority Queue after popping: ";
    pq.pop();
    while (!pq.empty()) {
        std::cout << pq.top() << " ";
        pq.pop();
    }
    std::cout << '\n';

    return 0;
}

```
