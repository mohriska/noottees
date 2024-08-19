# Structures


Like classes, structures also group together properties and methods used to represent an object and do specific tasks. 

There are differences between classes and structures though.

Structure names also should start with a capital letter

```
struct StructName { 
   property1 
   property2 
   property3
   method1() {
      code
   }
   method2(){
      code
   }
}
```

As you can see, a structure is very similar to a class. It also has a descriptive name, can contain properties and methods, and you can create instances.

## Creating a structure declaration

```
struct Reptile {
   
   var name: String 
   var sound: String
   var numberOfLegs: Int
   var breathesOxygen: Bool
   let hasFurOrHair: Bool = false 
   
   func makeSound() {
      print(sound)
   }
   
   func description() -> String {
      return "Structure: Reptile name: \(self.name) 
      sound: \(self.sound) 
      numberOfLegs: \(self.numberOfLegs)
      breathesOxygen: \(self.breathesOxygen) 
      hasFurOrHair: \(self.hasFurOrHair)"
   }
}

```

## Making an instance of the structure

* As with classes, you can create instances from a structure declaration.
* Structures automatically get an initializer for all their properties, called the memberwise initializer.

```
var snake = Reptile(name: "Snake", sound: "Hiss", 
numberOfLegs: 0, breathesOxygen: true)
print(snake.description())
snake.makeSound()
```


## Differences between class and structures

Even though the structure declaration is very similar to the class declaration, there are two differences between a class and a structure:

* Structures cannot be inherited from another structure
* Classes are reference types, while structures are value types

## Comparing value types and reference types

* Classes are reference types. This means when you assign a class instance to a variable, you are storing the memory location of the original instance in the variable, instead of the instance itself.

* Structures are value types. This means when you assign a structure instance to a variable, that instance is copied, and whatever changes you make to the original instance do not affect the copy.

## Deciding between classes and structures
* It is recommended to use structures unless you need something that requires classes, such as subclasses. This helps to prevent some subtle errors that may occur due to classes being reference types.