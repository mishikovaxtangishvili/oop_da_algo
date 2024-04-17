# პოინტერები კლასების იერარქიაში. ძირითადი ფაქტები და თვალსაჩინო მაგალითები

პოინტერების კლასების იერარქიაში გაგება საჭიროა პოლიმორფიზმის ფუნდამენტარული
გაგებისთვის

### მაგალითი 

```cpp
#include <iostream>

class Shape {
public:
    virtual ~Shape() {
        std::cout << "Shape class destructor\n";
    }

    virtual void display() {
        std::cout << "Shape class display function\n";
    }
};

class Rectangle : public Shape {
public:
    ~Rectangle() override {
        std::cout << "Rectangle class destructor\n";
    }

    void display() override {
        std::cout << "Rectangle class display function\n";
    }
};

int main() {
    Shape* ptr_base = new Rectangle(); 
    ptr_base->display(); 
    
    delete ptr_base;
}
```

> [!IMPORTANT]
> კოდის გაშვების დროს დააკვირდით რა მიხედვით იბეჭდება შეტყობინებები

1. Shape ტიპის პოინტერს შეუძლია შეინახოს Rectangle ტიპის ცვლადის მისამართი
რადგან Rectangle კლასს ყველაფერი აქვს რაც Shape-ს, **მაგრამ** Shape ტიპზე 
პოინტერის  გამოყენებით მარტო იმ წევრებთან და მეთოდებთან გვაქვს წვდომა რომლებიც 
Shape კლასში არის
2. მეხსიერების სწორი განთავისუფლების უზრუნველსაყოფად ფუძე კლასს აუცილებლად უნდა
ჰქონდეს ვირტუალური დესტრუქტორი
