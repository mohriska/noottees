# Classes

Classes are useful for representing complex objects.

* Every class has a descriptive name, and it contains variables or constants used to represent an object. Variables or constants associated with a class are called **properties**.

* A class can also contain functions that perform specific tasks. Functions associated with a class are called **methods**.

* Once you have declared and defined a class, you can create instances of that class.

* Convention dictates that class names start with a capital letter.

### Declaration template

```
class ClassName {
   property1
   property2 
   property3 
   method1() { 
      code
   }
   method2() {
      code
   }
} 

```


### Creating a class declaration

```
class Animal {
   var name: String = "" 
   var sound: String = ""
   var numberOfLegs: Int = 0
   var breathesOxygen: Bool = true
   func makeSound() {
      print(self.sound)
   }
}

```

## Making an instance of the class

```
let cat = Animal()
print(cat.name)
print(cat.sound)
print(cat.numberOfLegs)
print(cat.breathesOxygen)
cat.makeSound()
```

## Initializing

Note that here you create the instance first, and then assign values to that instance. It is also possible to assign the values when the instance is being created, and you do this by implementing an initializer in your class declaration.

The initializer uses the init keyword and has a list of parameters that will be used to set the property values.

```
class Animal {
   var name: String 
   var sound: String
   var numberOfLegs: Int
   var breathesOxygen: Bool

   init(name: String, sound: String, numberOfLegs: Int, breathesOxygen: Bool) {
      self.name = name
      self.sound = sound
      self.numberOfLegs = numberOfLegs
      self.breathesOxygen = breathesOxygen
   }

   func makeSound() {
      print(self.sound)
   }

   func description() -> String {
      return "name: \(self.name) 
      sound: \(self.sound)
      numberOfLegs: \(self.numberOfLegs)
      breathesOxygen: \(self.breathesOxygen)"
   }
}
```

and creating the object is:

```
let cat = Animal(name: "Cat", sound: "Mew", numberOfLegs: 4, breathesOxygen: true)
print(cat.name)

```


## Making a subclass

A subclass of a class inherits all the methods and properties of an existing class. You can also add additional properties and methods to it if you wish.

```
class Mammal: Animal {
   let hasFurOrHair: Bool = true
}
```

```
let cat = Mammal(name: "Cat", sound: "Mew", numberOfLegs: 4, breathesOxygen: true)
```

You have seen that a subclass can have additional properties. A subclass can also have additional methods, and method implementation in a subclass can differ from the superclass implementation.

## Overriding a superclass method

* keyword: **override**

```
Mammal: Animal {
   let hasFurOrHair: Bool = true
   override func description() -> String {
      return super.description() + " hasFurOrHair: 
      \(self.hasFurOrHair)"
   }
}
```