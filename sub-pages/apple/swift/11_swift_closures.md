# Closures

A closure, like a function, contains a sequence of instructions and can take arguments and return values.

Like functions, closures allow you to combine several instructions together, but closures do not have names and can be assigned to a constant or a variable. However, closures don’t have names. The sequence of instructions in a closure is surrounded by curly braces ({ }), and the in keyword separates the arguments and return type from the closure body.

Closures can be assigned to a constant or variable, so they’re handy if you need to pass them around inside your program. 

```
var numbersArray = [2, 4, 6, 7]
let myClosure = { (number: Int) -> Int in 
   let result = number * number
   return result
}


let mappedNumbers = numbersArray.map(myClosure)

```


## Simplifying closures

```
var testNumbers = [2, 4, 6, 7]
let mappedTestNumbers = testNumbers.map({ (number: Int) 
   -> Int in 
   let result = number * number
   return result
})
print(mappedTestNumbers)
```


When a closure’s type is already known, you can remove the parameter type, return type, or both. Single-statement closures implicitly return the value of their only statement, which means you can remove the return statement as well. So, you can write the closure as follows:

```
let mappedTestNumbers = testNumbers.map({ number in 
  number * number 
})
```

When a closure is the only argument to a function, you can omit the parentheses enclosing the closure, as follows:

```
let mappedTestNumbers = testNumbers.map { number in 
  number * number 
}
```

You can refer to parameters by a number expressing their relative position in the list of arguments instead of by name, as follows:

```
let mappedTestNumbers = testNumbers.map { $0 * $0 }
```