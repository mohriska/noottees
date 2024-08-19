# Protocols

* Protocols define a blueprint of methods, properties, and other requirements that can be adopted by a class, structure, or enumeration.

* Just like classes and structures, protocol names start with an uppercase letter.

* Properties are declared using the var keyword.

* You use **{get set}** if you want a property that can be read from or written to, and **{get}** if you want a read-only property.

* Note that you just specify property and method names; the implementation is done within the adopting class, structure, or enumeration.


```
protocol ProtocolName {
   var readWriteProperty1 {get set}
   var readOnlyProperty2 {get}
   func methodName1()
   func methodName2()
}
```

```
protocol CalorieCount {
   var calories: Int { get }
   func description() -> String
}
```


```
class Burger: CalorieCount {
   let calories = 800
   func description() -> String {
      return "This burger has \(calories) calories"
   }
}
```