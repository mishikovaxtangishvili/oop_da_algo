# შეგვიძლია თუ არა C++ ენის ბიბლიოთეკის ალგორითმის გამოყენებით მონაცემების კოპირება დიაპაზონიდან ფაილში? ეკრანზე? მოიყვანეთ მაგალითი.

კი, რამოდენიმე სტანდარტული ალგორითმის გამოყენებით როგორიცაა `std::copy`

### მაგალითები:

#### მონაცემების ფაილში კოპირება
```cpp
#include <iostream>
#include <fstream>
#include <vector>
#include <algorithm>

int main() {
    std::vector<int> data {1, 2, 3, 4, 5};

    std::ofstream file("output.txt");

    std::copy(data.begin(), data.end(), std::ostream_iterator<int>(file, " "));
    
    file.close();
}
```

#### მონაცემების ეკრანზე(კონსოლში) კოპირება

```cpp
#include <iostream>
#include <vector>
#include <algorithm>

int main() {
    std::vector<int> data {1, 2, 3, 4, 5};

    std::copy(data.begin(), data.end(), std::ostream_iterator<int>(std::cout, " "));
    std::cout << '\n';
    
    return 0;
}
```
