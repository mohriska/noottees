# Optionals

What if you require a variable where the value may not be present initially? You will need a way to create a variable that may or may not have a value. Swift allows you to do this by using **optionals**.

What if you want to declare a variable first and assign a value later? In this case, you would use **optionals**.

An **optional** may have one of two possible states. It can either contain a value or not contain a value. If an optional contains a value, you can access the value inside it. The process of accessing an optional’s value is known as **unwrapping** the optional.

### Example
* You may have a spouse or you may not


```
var spouseName: String = "" // it is emptyString... so it has a value
print(spouseName)           // prints empty string

var spouseName: String? // it is nil, so no value
print(spouseName)       // error, print expect a String not an optional.. you have to unwrap it

// you could do: 
print(spouseName ?? "No value in spouseName")
```


## Force Unwrapping

Force-unwrapping unwraps an optional whether it contains a value or not. It works fine if spouseName has a value, but if spouseName is nil, your program will crash.

```
let greeting = "Hello, " + spouseName!
```

## Optional Binding

 In optional binding, you attempt to assign the value in an optional to a temporary variable (you can name it whatever you like). If the assignment is successful, a block of code is executed.


 ```
spouseName = "Nia"
print(spouseName ?? "No value in spouseName")
if let spouseTempVar = spouseName {
   let greeting = "Hello, " + spouseTempVar 
   print(greeting)
}

 ```