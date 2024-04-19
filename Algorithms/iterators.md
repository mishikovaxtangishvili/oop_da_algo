# რა არის იტერატორი? რაში მდგომარეობს მისი გამოყენების აუცილებლობა და მოსახერხებლობა?

იტერატორები[^1] არიან ობიექტები რომლების დახმარებითაც შეგვიძლია რაიმე
კონტეინერის ელემენტები შემოვიაროთ. იტერატორები მოქმედებენ როგორც ობიექტების
პოინტერები და გვაძლევენ მიმდევრობით წვდომას კონტეინერის ელემენტებთან რაც
გვაძლევს ისეთი ოპერაციების შესრულების საშუალებას როგორიცაა წაკითხვა,
მოდიფიკაცია და წაშლა

მათი გამოყენების აუცილებლობა მდგომარეობს იმაში თუ რამდენად ამარტივებენ ისინი
კონტეინერების ელემენტების მანიპულაციას. ისინი ასევე ძალიან მოსახერხებლები არიან
იმ თვალსაზრისით რომ მნიშვნელობა არ აქვს რა კონტეინერს ვიყენებთ, `std::vector`-s,
`std::map`-s თუ `std::list`-ს მათი იტერატორების გამოყენებით ერთი და იგივე
ოპერაციების შესასრულებლად ერთი და იგივე ფუნქციონალს ვიყენებთ

### იტერატორების სხვადასხვა ტიპები და მათი შესაძლებლობები


| Iterator      | Capabilities                                               | 
|---------------|------------------------------------------------------------|
| Input         | `it++`, `*it`, `it == b`, `it != e`                        | 
| Output        | `it++`, `*it = value`                                      | 
| Forward       | `it++`, `*it`, `it == b`, `it != e`, `*it = value`         | 
| Bidirectional | `it++`, `--it`, `*it`, `it == b`, `it != e`, `*it = value` | 
| Random Access | `it++`, `--it`, `*it`, `it == b`, `it != e`, `*it = value`, `it += n`, `it -= n`, `it + n`, `it - n` | Requires support for arithmetic operations |


![Test](https://www.programiz.com/sites/tutorial2program/files/cpp-iterator-types.png "Testing")


[^1]: https://www.hackterms.com/iterate