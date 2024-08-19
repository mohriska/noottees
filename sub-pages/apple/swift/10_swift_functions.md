# Functions

Functions, which let you combine several instructions together and execute them by calling a single name.

### Content
1. Functions
2. Nested function
3. Functions as return types
4. Functions as arguments
5. GUARD statement



----

## Functions

Every function has a descriptive name. You can define one or more values that the function takes as input, known as parameters. You can also define what the function will output when done, known as its return type. Both parameters and return types are optional.

### Declaration of a function

```
func functionName(parameter1: ParameterType, ...) -> ReturnType {
   code
}
```

### Calling the function

```
functionName(parameter1: argument1, …)
```

### Example of function

```
// declarration function serviceCharge
func serviceCharge() {
   let mealCost = 50
   let serviceCharge = mealCost / 10
   print("Service charge is \(serviceCharge)")
}

// calling function serviceCharge
serviceCharge()
```

or 

```
// with return parameter
func serviceCharge(mealCost: Int) -> Int {
   return mealCost / 10
}

// storing return value
let serviceChargeAmount = serviceCharge(mealCost: 50)

print(serviceChargeAmount)

```

### Using custom argument labels

Note that the serviceCharge(mealCost:) function is not very English-like. You can add a custom label to the parameter to make the function easier to understand.

```
func serviceCharge(forMealPrice mealCost: Int) -> Int {
   // note that if your function body only consists of a single statement, the return keyword is optional.
   mealCost / 10
}

let serviceChargeAmount = serviceCharge(forMealPrice: 50)
print(serviceChargeAmount)

```


## Nested Functions

It’s possible to have a function within the body of another function, and these are called nested functions. A nested function can use the variables of the enclosing function.

```
func calculateMonthlyPayments(carPrice: Double, downPayment: Double, interestRate: Double, paymentTerm: Double) -> Double {
   func loanAmount() -> Double {
      return carPrice - downPayment
   }
   func totalInterest() -> Double {
      return interestRate * paymentTerm
   }
   func numberOfMonths() -> Double {
      return paymentTerm * 12
   }
   return ((loanAmount() + ( loanAmount() * 
   totalInterest() / 100 )) / numberOfMonths())
}


calculateMonthlyPayments(carPrice: 50000, downPayment: 5000, interestRate: 3.5, paymentTerm: 7.0)
```


## Function as Return types

As you have seen, functions in Swift are like functions in other languages, but they have a cool feature. Functions are first-class types in Swift, so they can be used as parameters and return types.

A function can return another function as its return type.

```
func makePi() -> (() -> Double) {
   func generatePi() -> Double {
      return 22.0 / 7.0
   }
   return generatePi
}

let pi = makePi()
print(pi())
```


## Function as Parameteres

A function can take another function as a parameter.

```
func isThereAMatch(listOfNumbers: [Int], condition: (Int) -> Bool) -> Bool {
   for item in listOfNumbers {
      if condition(item) {
         return true
      }
   }
   return false
}

func oddNumber(number: Int) -> Bool {
   return (number % 2) > 0
}

let numbersList = [2, 4, 6, 7]
isThereAMatch(listOfNumbers: numbersList, condition: oddNumber)
```


## Guard

Using a guard statement to exit a function early.

If there is something wrong with the input data, it is useful to be able to exit a function early.

Let’s see how this function works. The first line in the function body is a guard statement. This checks to see whether a condition is true; if not, it exits the function. Here, it is used to check and see whether the user entered a valid price in the online purchasing terminal. If so, the value can be converted successfully into an integer, and you can calculate the remaining card balance. Otherwise, the else clause in the guard statement is executed.

```
func buySomething(itemValueEntered itemValueField: String, cardBalance: Int) -> Int {
   guard let itemValue = Int(itemValueField) else {
      print("error in item value")
      return cardBalance
   }
   let remainingBalance = cardBalance - itemValue 
   return remainingBalance
}

print(buySomething(itemValueEntered: "10", cardBalance: 50))
print(buySomething(itemValueEntered: "blue", cardBalance: 50))
```