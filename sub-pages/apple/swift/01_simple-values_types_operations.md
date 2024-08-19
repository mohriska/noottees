# Simple Values, Operators, Types

## Constants and variables
* use camel case
* You can use constants or variables to store values. Both are containers that have a name, but a constant’s value can only be set once and cannot be changed after they are set, whereas a variable’s value can be changed at any time.

* You must declare constants and variables before you use them. Constants are declared with the let keyword while variables are declared with the var keyword.
```
// constant
let pi = 3.14159

// variable
var temp = 31

// variable with string literal
var myLocation = "Praha"
 
```

## Type inference and Type safety

### Type inference
Swift automatically determines the constant or variable type based on the value provided. This is called type inference.

_<u>NOTE: You can see the type of a constant or variable by holding down the Option key and clicking its name. </u>_

```
// type inference
let cuisine = "American"
```

### Type safety
* Using type annotation to specify a type.
* type a colon **(:)** after a constant or variable name, followed by the desired type. This is known as type annotation.

```
// type annotation
var restaurantRating: Double = 3
```


## Numeric

### Integers

* Integers in Swift are represented by the Int type.


```
// Integers examples
42
-23
```


### Floating-point numbers

* The default type for floating-point numbers in Swift is **Double**, which uses 64 bits, including negative numbers. 
* You can also use **Float**, which uses 32 bits, but Double is the default representation.

```
3.14159
-273.15
```

## Strings

* You would use Swift’s **String** type, which represents a sequence of characters and is fully Unicode-compliant.


```
"hello, world"
```

## Booleans

* Swift provides a **Bool** type that can be assigned true or false.

```
true
false
```


## Operators

### Numerical operators

* returns numerical values based on types

|Operrator| Description|Example |
|----|-----|----|
|+ |Addition|let sum = 23 + 20, let word = "ah" + "oj"|
|-|Subtraction|let ressult = 32 - sum|
|*|Multiplication|let total = 2 * 5|
|/|Division|let divide = total / 2|
|+=| Adds value and assign|d += 2 (short for d = d + 2)|
|-=|Subtra. and assign| d -= 2|
|*=|Multiplies and assign| d *= 2|
|/=|Divides and assign| d /= 2|

### Comparison operators

* returns Boolen values **true** or **false**

|Operrator| Description|Example |
|----|-----|----|
|==| Equal to| a == b|
|!=| Not equal to| a != b|
|>| Greater than | a > b|
|< |Less than | a < b|
|>= | Greater equal| a >= b|
|<=| Less than or equal to | a <= b|

### Logical operators

* Logical operators are handy when you deal with two or more conditions.

|Operrator| Description|Example |
|----|-----|----|
|&&| Logical AND| (a > b) && (b > c)|
|pipe pipe| Logical OR | |
|!| Logical NOT | !a or !(1 == 1)|





## References
* [Unicode](https://home.unicode.org/basic-info/faq/)