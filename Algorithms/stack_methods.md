# აღწერეთ სტეკის რამდენიმე მეთოდი. მოიყვანეთ მაგალითები.

1. **push()**: ელემენტს ამატებს სტეკში

```cpp
#include <iostream>
#include <stack>

int main() {
    std::stack<int> intStack;
    intStack.push(10);
    intStack.push(20);
    intStack.push(30);

    std::cout << "Top element after push: " << intStack.top() << '\n';

    return 0;
}
```

2. **pop()**: ზემოთა ელემენტს იღებს სტეკიდან

```cpp
#include <iostream>
#include <stack>

int main() {
    std::stack<int> intStack;
    intStack.push(10);
    intStack.push(20);
    intStack.push(30);

    intStack.pop();
    std::cout << "Top element after pop: " << intStack.top() << '\n';

    return 0;
}
```

3. **top()**: აბრუნებს სტეკის ზემოთა ელემენტზე რეფერენსს

```cpp
#include <iostream>
#include <stack>

int main() {
    std::stack<int> intStack;
    intStack.push(10);
    intStack.push(20);
    intStack.push(30);

    std::cout << "Top element: " << intStack.top() << '\n';

    return 0;
}
```

4. **empty()**: აბრუნებს true-ს თუ სტეკი ცარიელია, false-ს სხვა შემთხვევაში

```cpp
#include <iostream>
#include <stack>

int main() {
    std::stack<int> intStack;

    if (intStack.empty()) {
        std::cout << "Stack is empty" << '\n';
    } else {
        std::cout << "Stack is not empty" << '\n';
    }

    return 0;
}
```
