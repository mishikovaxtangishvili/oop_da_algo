# რა არის იტერატორების მახასიათებლების (std::iterator_traits<>) დანიშნულება? მოიყვანეთ მისი გამოყენების მაგალითი.

`std::iterator_traits<>` არის ზოგადი ტიპის ხელსაწყო რომელიც გამოიყენება
იტერატოზე ინფორმაციის მოსაპოვებლად, მაგალითად მისი საშუალებით შეგვიძლია პასუხი
გავცეთ შემდეგ შეკითხვებს

- "რა კატეგორიის იტერატორი გვაქ?"
- "იტერატორი რა ტიპის მონაცემს უთითებს"

`std::iterator_traits<>` მუშაობს ნებისმიერ იტერატორზე, პოინტერებზეც კი!

### მაგალითი
```cpp
#include <iostream>
#include <vector>
#include <iterator>

template <class ForwardIt>
void replacer(
    ForwardIt first,
    ForwardIt last,
    const typename std::iterator_traits<ForwardIt>::value_type old_value,
    const typename std::iterator_traits<ForwardIt>::value_type new_value
) {
    while (first != last) {
        if (*first == old_value) {
            *first = new_value;
        }
        ++first;
    }
}

int main() {
    std::vector<int> vec = {10, 20, 30, 30, 20, 10, 10, 20};
    replacer(vec.begin(), vec.end(), 20, 9999);

    std::cout << "Vector contains:";
    for (auto elemnt : vec) {
        std::cout << ' ' << elemnt;
    }

    std::cout << '\n';
}
```

ამ მაგალითში `std::iterator_traits<>` ის გამოყენებით ვიგებთ იმ მონაცემის ტიპს
რომელსაც ჩვენი იტერატორები უთითებენ და მაგ ტიპის მონაცემების დამატებით ორ
პარამეტრს ვითხოვთ
