# რა არის პრიორიტეტების რიგი? რომელი კონტეინერის ადაპტირება შეუძლია მას? მოიყვანეთ მაგალითები

პრიორიტეტების რიგი არის მონაცემთა სტრუქტურა რომელიც ძალიან გავს ჩვეულებრივ რიგს
ერთი განსხვავებით. პრიორიტეტების რიგში ელემენტები მათი პრიორიტეტულობის მიხედვით
მოგვაქ და არა მათი ჩასმის დროით, მაღალი პრიორიტეტების მქონე ელემენტები პირველები
მოგვაქ პრიორიტეტების რიგში. პრიორიტეტების რიგები ხშირად იმპლემენტირებულები არიან
გროვების (Heap) დახმარებით, გროვა სპეციალიზირებული ხეებზე დაფუძნებული მონაცემთა
სტრუქტურაა რომელიც საშუალებას გვაძლევს რომ პრიორიტეტის მაღალი/დაბალი მქონე
ელემენტები ეფექტურად ჩავსვათ/წამოვიღოთ

`std::priority_queue` default-ზე `std::vector` ის ადაპტაცის ახდენს, მაგრამ მას
ასევე შეუძლია `std::deque`ს ადაპტაცია

```cpp
#include <iostream>
#include <queue>
#include <vector>
#include <deque>

int main() {
    std::priority_queue<int, std::vector<int>> vectorPriorityQueue;
    vectorPriorityQueue.push(30);
    vectorPriorityQueue.push(10);
    vectorPriorityQueue.push(50);

    std::cout << "Priority Queue using std::vector: ";
    while (!vectorPriorityQueue.empty()) {
        std::cout << vectorPriorityQueue.top() << " ";
        vectorPriorityQueue.pop();
    }
    std::cout << '\n';

    std::priority_queue<int, std::deque<int>> dequePriorityQueue;
    dequePriorityQueue.push(300);
    dequePriorityQueue.push(100);
    dequePriorityQueue.push(500);

    std::cout << "Priority Queue using std::deque: ";
    while (!dequePriorityQueue.empty()) {
        std::cout << dequePriorityQueue.top() << " ";
        dequePriorityQueue.pop();
    }
    std::cout << '\n';

    return 0;
}
```
