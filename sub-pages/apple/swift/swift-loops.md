# Swift Loops

## For In Loops

```
let names = ["Anna", "Alex", "Brian", "Jack"]
for name in names {
    print("Hello, \(name)")
}
```

or inside of range

```
for number in 1...5 {

}
```

or if we do not need a value

```
for _ in 1...5 {
    print("Hello")
}
```


* check differences between **Array** and **Set**


## For In for Dictionaries

```
let contacts = ["Adam": 123456789, "James":987654321, "Amy":912837653]

for person in contacts {
    print(person.key)
    print(person.value)
}
```


## While loops

```
var now = Date().timeIntervalSince1970
let oneSecondFromNow = now + 1

while now < oneSecondFromNow {
    ...
}
```