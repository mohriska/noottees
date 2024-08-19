# Arrays

An array stores values in an _ordered_ list. Values must be of the same type. You can access any value in an array by using the array index, which starts with 0.

If you create an array using the **let** keyword, its contents can’t be changed after it has been created. If you want to change an array’s contents after creation, use the **var** keyword.


```
var shoppingList = ["Eggs", "Milk"]
```



## Array methods
* shoppingList.count 
* shoppingList.isEmpty
* shoppingList.append("Cooking Oil")
* shoppingList = shoppingList + ["Cooking Oil"] 
* shoppingList.insert("Chicken", at: 1)


## Accessing an array element
* shoppingList[2]
* shoppingList[2] = "Soy Milk"

## Removing an element from an array
```
shoppingList.remove(at: 1)
shoppingList.removeLast()
```

## Iterating over an array


```
for shoppingListItem in shoppingList {
   print(shoppingListItem)
}
```

```
for shoppingListItem in shoppingList[1...] {
   print(shoppingListItem)
}
```