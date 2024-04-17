# ფუძე კლასი და წარმოებული კლასი. ძირითადი ფაქტები და თვალსაჩინო მაგალითები.

1. ფუძე კლასი, ასევე ცნობილი როგორც მშობელი კლასი ან სუპერკლასი, არის კლასი
რომელიც გამოიყენება როგორც საფუძველი სხვა კლასებისთვის. მასში ავღწერთ ზოგად
ატრიბუტებს და ფუნქციონალს რომელებიც შვილობილ კლასებს მემკვიდრეობით გადაეცემათ.

2. წარმოებული კლასი, უფრო ცნობილი როგორც შვილობილი კლასი ან ქვეკლასი, არის კლასი
რომელიც მემკვიდრეობით იღებს ატრიბუტებს და ფუნქციონალს მშობელი კლასისგან. მას
შეუძლია მშოებლი კლასის ფუნქციონალი შეცვალოს ან გაზარდოს ახალი წევრების დამატებით
ან არსებული წევრებზე ახალების გადაწერით

### მაგალითი
```cpp
#include <iostream>

class Shape {
public:
    double width;
    double height;

    void setWidth(const double w) {
        width = w;
    }

    void setHeight(const double h) {
        height = h;
    }

    virtual double area() {
        return 0.0;
    }
};

class Rectangle : public Shape {
public:
    double area() override {
        return width * height;
    }
};

int main() {
    Rectangle rect;
    rect.setWidth(5.0); // Rectangle კლასის ობიექტს ყველაფერი აქვს რაც Shape-ს
    rect.setHeight(3.0);

    std::cout << "Area of rect: " << rect.area() << '\n'; //და მეტიც რაც დაამატა
}
```

1. შევქმენით ფუძე კლასი `Shape` ორი ატრიბუტით და ორი მეთოდით
2. `Shape` კლასს ასევე აქვს ვირტუალური[^1] მეთოდი `area()`, შვილობილი კლასები ამ
მეთოდს გადააწერენ თავიანთი ვერსიებით
3. შევქმენით კლასი `Rectangle` რომელიც `Shape` კლასის მემკვიდრეა
4. `Rectangle` კლასში არსებული `area()` მეთოდი გადააწერს მშოებლი კლასის მეთოდს
და გამოითვლის ფართობს ზუსტად მართკუთხედებისთვის


### შვილობილი კლასის გამოცხადების ანატომია
```cpp
class <კლასის_სახელი> : <წვდომის_ტიპი> <მშობელი_კლასის_სახელი> {
    
}
```

[^1]: ვირტუალური ფუნქციები არიან სპეციალური ტიპის მეთოდები ფუძე კლასებში
რომლებიც გადაწერილები იქნებიან შვილობილი კლასების მეთოდების მიერ