# Functions in Swift

1. Function without parameters and output
2. Function with parameters and no output
3. Function with input and output parameters
4. Clousures



## Parameter Names
* internal parameter name: <eman>
* external parameter name: <name>
* external parameter name: _

```
func myFunc(name eman: Type){
    print(eman)
}

myFunc(name: "Martin")


// OR

func myFunc(_ eman: Type){
    print(eman)
}

myFunc("Martin")


```


## 1. Function without parameters and output

```
func doPrint(){
    print("Hi")
}
```


## 2. Function with parameters and no output
```
func doPrintName(name: String){
    print("Hi /(name)")
}
```

## 3. Function with input and output parameters

```

func getMilk(money: Int) -> Int{
    let change =  money - 2
    return change
}

getMilk(4)
```


## 4. Closures
```
{ (<parameter list>) -> <return type> in 
    <code>
}

// or shorter --- $0 and $1 are parameters and everything else is infered (return type and parameter list)
{ $0 * $1}
```

```

func calculator(n1: Int, n2: Int, operation: (Int, Int) -> Int) -> Int{
    return operation(n1, n2)
}

calculator(n1: 2, n2: 3, { (no1: Int, no2: Int) -> Int in
    return no1 + no2
})

// trailing closures (same result as above)
calculator(n1: 2, n2: 3) {$0 * $1}

```