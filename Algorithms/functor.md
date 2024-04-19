# მოიყვანეთ ფუნქტორის (იგივეა რაც ფუნქციური ობიექტი ან გამოძახებადი ობიექტი) გამოყენების მაგალითები. რა უპირატესობა აქვს ფუნქტორს ჩვეულებრივ ფუნქციასთან შედარებით?

ფუნქტორები არიან სპეციალური ტიპის ობიექტები რომლებიც ფუნქციებისავით შეგვიძლია
გამოვიძახოთ. ისინი ამას ფუნქციის გამოძახების `operator()` გადატვირთვით ახერხებენ

ფუნქტორების უპირატესობა მდგომარეობს იმაში რომ მათ შეუძლიათ ობიექტზე
ორიენტირებული პარადიგმის პრინციპების გამოყენება როგორიცაა ენკაპსულაცია და 
პოლიმორფიზმი. მათ ასევე შეუძლიათ თავიანთი ფუნქციონალი შეცვალონ ინიციალიზაციის
დროს სხვადასხვა კონსტრუქტორების  დახმარებით.

### მაგალითი: 

```cpp
#include <iostream>
#include <algorithm>
#include <vector>

class string_len_compare {
public:
    bool operator()(const std::string& a, const std::string& b) const {
        return a.length() < b.length();
    }
};

int main() {
    std::vector<std::string> words = {"apple", "banana", "orange", "grape"};
    
    std::sort(words.begin(), words.end(), string_len_compare());
    
    for(const auto& word : words) {
        std::cout << word << " ";
    }
    std::cout << std::endl;
}
```

