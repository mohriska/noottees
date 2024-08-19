# Extensions

* Extensions enable you to provide new functionality for an existing class, structure, or enumeration.

* Extensions allow you to provide extra capabilities to an object without modifying the original object definition. You can use them on _Apple-provided objects_ (where you don’t have access to the object definition) or when you wish to segregate your code for readability and ease of maintenance.

```
class ExistingType {
   property1
   method1()
}
extension ExistingType : ProtocolName {
   property2
   method2()
}
```


```
enum Sauce {
   case chili 
   case tomato
}


extension Sauce: CalorieCount {
   var calories: Int {
      switch self {
      case .chili:
         return 20 
      case .tomato: 
         return 15
      }
   }
   func description() -> String {
      return "This sauce has \(calories) calories"
   }
}
```

```
let burger = Burger()
let fries = Fries()
let sauce = Sauce.tomato

let foodArray: [CalorieCount] = [burger, fries, sauce]

var totalCalories = 0
for food in foodArray {
   totalCalories += food.calories
}
print(totalCalories)

```