# Conditionals



### Content
1. IF statement
2. SWITCH statement


## IF 

An if statement executes a block of code if a condition is true, and optionally, another block of code if the condition is false.

```
if condition {
   code1
} else {
   code2
}
```

```
let isRestaurantOpen = true 
if isRestaurantOpen {
   print("Restaurant is open.")
}
```
### NOT OPERATOR
```
let isRestaurantOpen = false 
if !isRestaurantFound{
   print("Restaurant is found.")
}
```
### Greater/Less Operator

```
let drinkingAgeLimit = 21 
let customerAge = 23
if customerAge < drinkingAgeLimit {
   print("Under age limit")
} else {
   print("Over age limit")
}
```

### ELSE IF

```
var trafficLightColor = "Yellow"
if trafficLightColor == "Red" {
   print("Stop")
} else if trafficLightColor == "Yellow" {
   print("Caution")
} else if trafficLightColor == "Green" {
   print("Go")
} else {
   print("Invalid color")
}
```

## SWITCH


```
switch value {
case firstValue:
   code1
case secondValue:
   code2
default: 
   code3
}
```