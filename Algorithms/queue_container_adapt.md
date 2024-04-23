# რატომ ეწოდება რიგს კონტეინერის ადაპტერი? რომელი კონტეინერის ადაპტირება შეუძლია მას? მოიყვანეთ მაგალითები.

რიგს კონტეინერის ადაპტერი ეწოდება იმიტომ რომ იმის მაგივრად რო თავისი
ელემენტების შესანახი სტრუქტურის იმპლემენტაციის ნაცვლად უკვე არსებულ კონტეინერ
სტრუქტურებს იყენებს და მათ ადაპტაციას ახდენს FIFO[^1] პრინციპის დასაცავად.
რიგი ამის დახმარებით საშუალებას გვაძლევს რომ მის მიერ ადაპტირებული კონტეინერის
ფუნქციონალი სპეციფიური გზით გამოვიყენოთ.

სტანდარტული ბიბლიოთეკის რიგი default-ზე `std::deque`-ს იყენებს მაგრამ მას ასევე
`std::vector` და `std::list` ის ადაპტირებაც შეუძლია

```cpp
#include <iostream>
#include <queue>
#include <deque>
#include <list>
#include <vector>

int main() {
    std::queue<int, std::list<int>> listQueue;
    listQueue.push(4);
    listQueue.push(5);
    listQueue.push(6);

    std::cout << "Queue using std::list: ";
    while (!listQueue.empty()) {
        std::cout << listQueue.front() << " ";
        listQueue.pop();
    }
    std::cout << '\n';

    std::queue<int, std::vector<int>> vectorQueue;
    vectorQueue.push(7);
    vectorQueue.push(8);
    vectorQueue.push(9);

    std::cout << "Queue using std::vector: ";
    while (!vectorQueue.empty()) {
        std::cout << vectorQueue.front() << " ";
        vectorQueue.pop();
    }
    std::cout << '\n';

    return 0;
}
```
[^1]: First In First Out
