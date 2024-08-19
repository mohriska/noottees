# Loops

Loops allow you to repeat an instruction or a sequence of instructions over and over. You can repeat a sequence a fixed number of times or repeat a sequence until a condition is met. 


There are three loop types: the **for-in** loop, the **while** loop, and the **repeat-while** loop. The **for-in** loop will repeat for a known number of times, and the **while** and **repeat-while** loops will repeat if the loop condition is **true**.



### Content
1. for-in
2. while
3. repeat-while



---

## for-in 
 
For-in loop is used when you know how many times a loop should be repeated.

```
for item in sequence {
   code
}
```

```
for number in myRange {
   print(number)
}
```

or

```
for number in 0...5 {
   print(number)
}
```

or reversed

```
for number in (0...5).reversed() {
   print(number)
}
```

## while

A while loop contains a condition and a set of statements in curly braces, known as the loop body. The condition is checked first; if true, the loop body is executed, and the loop repeats until the condition is false. 

```
while condition == true {
   code
}
```

```
var y = 0
while y < 50 {
   y += 5
   print("y is \(y)")
}
```


## repeat-while

Like a while loop, a repeat-while loop also contains a condition and a loop body, but the loop body is executed first before the condition is checked. If the condition is true, the loop repeats until the condition returns false. 

```
repeat {
   code
} while condition == true
```

```
var x = 0
repeat {
   x += 5
   print("x is \(x)")
} while x < 50
```

