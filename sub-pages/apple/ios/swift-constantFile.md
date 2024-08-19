# Using Constant File and keyword "static"


1. Create **Constants.swift** in the root of the project (or call it just "K")
2. Create struct like this

```
struct Constants { // or K, for short
    static let registerSegue = "RegisterToChat"
    static let loginSegue = "LoginToChat"
}
```

3. In the controller use it like this: 

```
... // some code
    Constants.registerSegue // or K.registerSegue
... // some more code
``` 


## Static

- public, not needed to create reference for the struct in target controller
- example above

