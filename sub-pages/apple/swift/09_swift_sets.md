# Sets

A **set** stores values in an unordered list. All values are of the same type.

If you create a set using the **let** keyword, its contents can’t be changed after it has been created. If you want to change the contents after creation, use the **var** keyword.


## Creating a set

```
var movieGenres: Set = ["Horror", "Action", "Romantic Comedy" ]
```

## Checking the number of elements in a set

```
// check count
movieGenres.count


// chcek if empty
movieGenres.isEmpty
```

## Adding a new element to a set

```
movieGenres.insert("War")
```

## Checking whether a set contains an element

```
movieGenres.contains("War")
```

## Removing an item from a set

To remove an item from a set, use remove(_:). The value you are removing can be assigned to a variable or a constant. If the value doesn’t exist in the set, nil will be returned.

```
var oldSetValue = movieGenres.remove("Action")
```

To remove all the elements from a set, use removeAll().

```
movieGenres.removeAll()
```

## Iterating over a set

As with arrays and dictionaries, you can use a for-in loop to iterate over every element in a set. Since sets are unsorted, you may get the results in a different order when you run this code again.

```
for genre in movieGenres {
   print(genre)
}
```

## Performing set operations


```
let movieGenres2: Set = ["Science Fiction", "War", "Fantasy"]
movieGenres.union(movieGenres2)
movieGenres.intersection(movieGenres2)
movieGenres.subtracting(movieGenres2)
movieGenres.symmetricDifference(movieGenres2)
```


## Understanding set membership and equality

```
let movieGenresSubset: Set = ["Horror", "Romantic Comedy"]
let movieGenresSuperset: Set = ["Horror", "Romantic Comedy", "War", "Science Fiction", "Fantasy"]
let movieGenresDisjoint: Set = ["Bollywood"]
movieGenres == movieGenres2
movieGenresSubset.isSubset(of: movieGenres)
movieGenresSuperset.isSuperset(of: movieGenres)
movieGenresDisjoint.isDisjoint(with: movieGenres)

```