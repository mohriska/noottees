# Optionals

1. Force Unwrapping 
2. Check for **nil** value
3. Optional Binding
4. Nic Coalescing Operator
5. Optional Chaining


<hr>


### 1. Force Unwrapping

- least safe way to work with optionals
- creator should be sure that the OPTIOANL will never be **nil** 

```
optional!
```


### 2. Check for **nil** value

- check if optional is nil 

```
if optional != nil { 
    optional! 
} else {

    ... some code ...
}
```

### 3. Optional Binding

- same as before version, but upgrade

```
if let safeOptional = optional {
    safeOptional
} else {
    ... some code ...
}
```

### 4. Nil Coalescing Operator

- provides default value

```
// optional ?? defaltValue

let myOptional: String?
myOptional = nil

let text: String = myOptional ?? "I am the default value"
print(text)
```

### 5. Optional Chaining

```
// optional?.property
// optional?.method()

struct MyOptional {
    var property = 123
    func method(){
        print("I am the struct's method")
    } 
}

let myOptional: MyOptional?
myOptional = nil
print(myOptional?.property)

```