# Error Handling

* Error handling covers how to respond to and recover from errors in your program.

* When you write apps, bear in mind that error conditions may happen, and error handling is how your app would respond to and recover from such conditions.

```
do {
   try expression1
   statement1
} catch {
   statement2
}
```
* Here, you attempt to execute code in the do block using the try keyword. If an error is thrown, the statements in the catch block are executed. 

* You can have multiple catch blocks to handle different error types.

```
enum WebsiteError: Error {
   case noInternetConnection
   case siteDown
   case wrongURL
}

func checkWebsite(siteUp: Bool) throws -> String {
   if siteUp == false {
     throw WebsiteError.siteDown
   }
   return "Site is up"
}

...

let siteStatus = true
try checkWebsite(siteUp: siteStatus)


```

or better:

```
let siteStatus = false

do {
   print(try checkWebsite(siteUp: siteStatus))
} catch {
   print(error)
}

```
* The do block tries to execute the checkWebsite(siteUp:) function and prints the status if successful. If there is an error, instead of crashing, the statements in the catch block are executed, and the error message siteDown appears in the Debug area.