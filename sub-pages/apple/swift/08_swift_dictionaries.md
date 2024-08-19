# Dictionaries

A dictionary stores key-value pairs in an unordered list.


All keys must be of the same type and must be unique. All values must be of the same type, but are not necessarily unique. Keys and values don’t have to be of the same type as each other. You use the key to get the corresponding value.

If you create a dictionary using the let keyword, its contents can’t be changed after it has been created. If you want to change the contents after creation, use the var keyword

## Creating a dictionary

```
var contactList = ["Shah" : "+60123456789", "Aamir" : "+0223456789"]
```

## Checking the number of elements in a dictionary

```
// how many elements there are in a dictionary 
contactList.count

// check whether a dictionary is empty by using isEmpty
contactList.isEmpty
```

## Adding a new element to a dictionary
```
contactList["Jane"] = "+0229876543"
```

## Accessing a dictionary element
```
contactList["Shah"]
```

## Assigning a new value to an existing key

```
contactList["Shah"] = "+60126789345"
```

## Removing an element from a dictionary

```
contactList["Jane"] = nil

// retain the value you are removing
var oldDictValue = contactList.removeValue(forKey: "Aamir")
```

## Iterating over a dictionary

This prints every element in the dictionary to the Debug area. Since dictionaries are unordered, you may get the results in a **different order when you run this code again**.

```
for (name, contactNumber) in contactList {
   print("\(name) : \(contactNumber)")
}
```

