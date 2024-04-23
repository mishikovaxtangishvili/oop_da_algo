# რატომ ეწოდება სტეკს კონტეინერის ადაპტერი? რომელი კონტეინერის ადაპტირება შეუძლია მას? მოიყვანეთ მაგალითები

სტეკს კონტეინერის ადაპტერი ეწოდება იმიტომ რომ იმის მაგივრად რო თავისი
ელემენტების შესანახი სტრუქტურის იმპლემენტაციის ნაცვლად უკვე არსებულ კონტეინერ
სტრუქტურებს იყენებს და მათ ადაპტაციას ახდენს LIFO[^1] პრინციპის დასაცავად.
სტეკი ამის დახმარებით საშუალებას გვაძლევს რომ მის მიერ ადაპტირებული კონტეინერის
ფუნქციონალი სპეციფიური გზით გამოვიყენოთ.

სტანდარტული ბიბლიოთეკის სტეკი default-ზე `std::deque`-ს იყენებს მაგრამ მას ასევე
`std::vector` და `std::list` ის ადაპტირებაც შეუძლია

### მაგალითი

```cpp
#include <iostream>
#include <stack>
#include <vector>

int main() {
    // std::vector ის ადაპტირება
    std::stack<int, std::vector<int>> stackWithVector;

    // default-ზე std::deque ს ადაპტირება ხდება
    std::stack<int> stackWithDeque;

    stackWithVector.push(10);
    stackWithVector.push(20);
    stackWithDeque.push(30);
    stackWithDeque.push(40);

    std::cout << "Top element of stackWithVector: " << stackWithVector.top() << std::endl;
    std::cout << "Top element of stackWithDeque: " << stackWithDeque.top() << std::endl;

    return 0;
}
```

[^1]: Last In First Out
