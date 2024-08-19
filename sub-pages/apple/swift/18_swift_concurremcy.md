# Concurrency


* async/await
* async/let

In Swift 5.5, Apple added support for writing asynchronous and parallel code in a structured way.

_Asynchronous code allows your app to suspend and resume code. This allows your app to do things like update the user interface while still performing operations like downloading data from the internet._

Parallel code allows your app to run multiple pieces of code simultaneously.

## Using async-await

```
func methodName() async -> returnType {

}

await methodName()

```

## Improving efficiency using async-let

Writing async in front of a let statement when you define a constant, and then writing await when you access the constant, allows parallel execution of asynchronous methods. 

```
async let temporaryConstant1 = methodName1()
async let temporaryConstant2 = methodName2()
await variable1 = temporaryConstant1
await variable2 = temporaryConstant1
```

## More to learn
There is still lots more to learn about Swift concurrency, such as structured concurrency and actors, but that is beyond the scope of this chapter. You can learn more about structured concurrency at https://developer.apple.com/videos/play/wwdc2021/10134/, and you can learn more about actors at https://developer.apple.com/videos/play/wwdc2021/10133/.


### reference
* [async/await](https://developer.apple.com/videos/play/wwdc2021/10132/)
