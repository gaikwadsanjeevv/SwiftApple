# Learn SWIFT

Swift is primarily known for iOS, macOS, watchOS, and tvOS application development, but its use has expanded beyond just mobile app development. 
Here are some other areas where you can use Swift:
### iOS and macOS Applications
iOS Development: Swift is the primary language for building iOS applications. You can create apps for iPhones and iPads.
macOS Development: You can also develop applications for macOS using Swift.
### Web Development
Server-Side Swift: Swift can be used for backend development. Frameworks like Vapor and Kitura allow you to build server-side applications with Swift.
Vapor: A popular web framework for building web applications and APIs.
Kitura: Developed by IBM, Kitura is another framework for building web applications in Swift.
### Cross-Platform Development
Swift on Linux: Swift can be compiled and run on Linux, enabling you to build cross-platform applications that run on different operating systems.
### APIs and Microservices
Swift can be used to build RESTful APIs and microservices, enabling communication between different services and applications.
### Command-Line Tools
You can create command-line applications with Swift. These are useful for automation, scripting, and utilities.
### Game Development
While not as common as Objective-C or C#, Swift can be used with frameworks like SpriteKit and SceneKit for game development, especially for 2D and 3D games on iOS and macOS.
### Machine Learning
Swift can also be integrated with Core ML for machine learning models, allowing you to incorporate machine learning into your iOS and macOS applications.
### SwiftUI
SwiftUI is a framework that allows for building user interfaces across all Apple platforms using Swift. It's a modern way to create UI in a declarative style.
### Embedded Systems
Swift can be used for embedded programming, allowing you to develop applications that run on embedded devices.
### WebAssembly
Swift can be compiled to WebAssembly, enabling you to run Swift code in the browser, though this is still an emerging area.


## Basic Programming
```swift
==> In Swift, this line of code is a complete program. You don’t need to import a separate library for functionality like outputting text or handling strings.
Code written at global scope is used as the entry point for the program, so you don’t need a main() function. You also don’t need to write semicolons at the end of every statement.
code: 
print("Hello sanjeev")

==> The value of a constant can’t be changed once it’s set, whereas a variable can be set to a different value in the future. 
You declare constants with the let keyword and variables with the var keyword. 
code: 

let MaxNumberOfAttempts = 10;
var CurrentLoginAttempt = 2;


In this example below, the maximum number of login attempts is constant, and its value depends on the environment. 
In the development environment, it has a value of 100; in any other environment, its value is 10.


var environment = "Development"
let maxNumAttempts : Int
if environment = "Development" {
    maxNumAttempts = 100
}else {
    maxNumAttempts = 2
}


==> You can declare multiple constants or multiple variables on a single line, separated by commas:
var x=0.0, y = 0.1, z = 0.6


==> You can provide a type annotation when you declare a constant or variable, to be clear about the kind of values the constant or variable can store.

var welcomeMsg : string
welcomeMsg = "Sanjeev is best"


==> You can define multiple related variables of the same type on a single line, separated by commas, with a single type annotation after the final variable name:
Unlike a variable, the value of a constant can’t be changed after it’s set. Attempting to do so is reported as an error when your code is compiled:


==> In Swift, you can use reserved keywords as variable names or constants by surrounding them with backticks (`). 
Ex :  let `class` = “My class”    //try avoiding it

var `class` = 43
`class` = 32
print(`class`)


By default, print adds a newline (\n) after each print statement:
let message = “GunMan”
print(message)
//GunMan

You can use the separator parameter to specify what separates multiple values in a single print statement. The default separator is a space (" "), but you can change it:
Code: 
let firstName = "John"
let lastName = "Doe"
print(firstName, lastName, separator: " * ")
// John * Doe


==> Using the terminator parameter
By default, print terminates with a newline (\n), but you can change this behavior using the terminator parameter. For example, to print without a newline:
let firstName = "sanjeev"
let middleName = "venkati"
let lastName = "Gaikwad"
print(firstName, terminator: " ~ ")
print(lastName)
// sanjeev ~ Gaikwad


==> Combining separator and terminator
You can combine both separator and terminator parameters to control how multiple values are printed and how the output ends:
let fruit = ["apple", "banana", "orange"]
print(fruit[0],fruit[1],fruit[2], separator: " & ", terminator: "!")

// apple & banana & orange!


⇒ Swift uses string interpolation to include the name of a constant or variable as a placeholder in a longer string, and to prompt Swift to replace it
with the current value of that constant or variable. Wrap the name in parentheses and escape it with a backslash before the opening parenthesis:
Code:
let animalName = "Horse"
print("The name of the animal is \(animalName)")
//The name of the animal is Horse.


Unlike multiline comments in C, multiline comments in Swift can be nested inside other multiline comments.
// single line comment
/*
/*
Nested multi line comment
*/
*/


Why use nested multi-line comments?
Debugging large code blocks: When you want to comment out large sections of code for debugging purposes, and that code already contains multi-line comments, 
the ability to nest comments prevents conflicts.
Temporary code disabling: It allows you to disable or skip over sections of code that are no longer relevant without removing the existing comments inside.
⇒ Unlike many other languages, Swift doesn’t require you to write a semicolon (;) after each statement in your code, although you can do so if you wish.
However, semicolons are required if you want to write multiple separate statements on a single line:
let name = "sanjeev Gaikwad"; print(name)

==> Swift doesn’t require you to write a semicolon (;) after each statement in your code, although you can do so if you wish. However, semicolons are required if you want to write multiple separate statements on a single line:
let Animal = "Deer" ; print(Animal)

==>Integers are whole numbers with no fractional component, such as 42 and -23. Integers are either signed (positive, zero, or negative) or unsigned (positive or zero)

==> Swift also provides an unsigned integer type, UInt, Use UInt only when you specifically need an unsigned integer type with the same size as the platform’s native word size.
 If this isn’t the case, Int is preferred, even when the values to be stored are known to be nonnegative.

==> Floating-point numbers are numbers with a fractional component, such as 3.14159, 0.1, and -273.15.
Swift provides two signed floating-point number types: Double, Float
Double has a precision of at least 15 decimal digits, whereas the precision of Float can be as little as 6 decimal digits.

** Type Safety & Type Inference
--> Swift is type safe, it performs type checks when compiling your code and flags any mismatched types as errors.
--> If you don’t specify the type of value you need, Swift uses type inference to work out the appropriate type.
Type inference enables a compiler to deduce the type of a particular expression automatically when it compiles your code, simply by examining the values you provide.
code:
let meaningOfLife = 42   //type inference enable compiler to declare it as Int
let pi = 3.14159 //type inference enable compiler to declare it as float value based on value.

--> Swift always chooses Double (rather than Float) when inferring the type of floating-point numbers.
--> If you combine integer and floating-point literals in an expression, a type of Double will be inferred from the context:
let anotherPi = 3 + 0.14159
// anotherPi is also inferred to be of type Double

==> Type aliases define an alternative name for an existing type. You define type aliases with the typealias keyword.
Code :
typealias AudioSample = UInt16
//Once you define a type alias, you can use the alias anywhere you might use the original name:
var maxAmplitudeFound = AudioSample.min
// maxAmplitudeFound is now 0

### Boolean
Swift has a basic Boolean type, called Bool. Boolean values are referred to as logical, because they can only ever be true or false.
Code: 
if turnipsAreDelicious {
    print("Mmm, tasty turnips!")
} else {
    print("Eww, turnips are horrible.")
}
// Prints "Eww, turnips are horrible."
### Tuple
-->Tuples group multiple values into a single compound value. The values within a tuple can be of any type and don’t have to be of the same type as each other.
(404, "Not Found") is a tuple that describes an HTTP status code.

let http404Error = (404, "Not Found")
// http404Error is of type (Int, String), and equals (404, "Not Found")

--> You can decompose a tuple’s contents into separate constants or variables, which you then access as usual:
Code: 
let (statusCode, statusMessage) = http404Error
print("The status code is \(statusCode)")
// Prints "The status code is 404"
print("The status message is \(statusMessage)")
// Prints "The status message is Not Found"

--> If you only need some of the tuple’s values, ignore parts of the tuple with an underscore (_) when you decompose the tuple:

code:
let (justTheStatusCode, _) = http404Error
print("The status code is \(justTheStatusCode)")
// Prints "The status code is 404"

--> Alternatively, access the individual element values in a tuple using index numbers starting at zero:
print("The status code is \(http404Error.0)")
code:
// Prints "The status code is 404"
print("The status message is \(http404Error.1)")
// Prints "The status message is Not Found"

--> You can name the individual elements in a tuple when the tuple is defined:
let http200Status = (statusCode: 200, description: "OK")

--> If you name the elements in a tuple, you can use the element names to access the values of those elements:

print("The status code is \(http200Status.statusCode)")
// Prints "The status code is 200"
print("The status message is \(http200Status.description)")
// Prints "The status message is OK"

Tuples are particularly useful as the return values of functions.

Note :  #### Tuples are useful for simple groups of related values. They’re not suited to the creation of complex data structures.
 If your data structure is likely to be more complex, model it as a class or structure, rather than as a tuple.

## Optionals
You use optionals in situations where a value may be absent. An optional represents two possibilities:
Either there is a value of a specified type, and you can unwrap the optional to access that value, or there isn’t a value at all.

Code:
let possibleNumber = "123"
let convertedNumber = Int(possibleNumber)
// The type of convertedNumber is "optional Int"

Because the initializer in the code above might fail, it returns an optional Int, rather than an Int.    

## nil
You set an optional variable to a valueless state by assigning it the special value nil:
code:
var serverResponseCode: Int? = 404
// serverResponseCode contains an actual Int value of 404
serverResponseCode = nil
// serverResponseCode now contains no value

If you define an optional variable without providing a default value, the variable is automatically set to nil:

var surveyAnswer: String?
// surveyAnswer is automatically set to nil

Note: #### You can’t use nil with non-optional constants or variables. If a constant or variable in your code needs to work with the absence of a value under certain conditions, declare it as an optional value of the appropriate type. A constant or variable that’s declared as a non-optional value is guaranteed to never contain a nil value. If you try to assign nil to a non-optional value, you’ll get a compile-time error.

## Optional Binding
In Swift, optional binding is a way to safely unwrap an optional to access its value. An optional in Swift is a variable that can either hold a value or be nil (which means "no value"). Since directly accessing a nil optional can cause runtime errors, optional binding is used to check if the optional contains a value, and if it does, safely extract it.

### Why do we need optional binding?
Optional binding ensures that we only attempt to use the value if it actually exists, preventing crashes.
 This is particularly useful when working with data that may or may not be present, like API responses or user input.

var name: String? = "Alice"
if let unwrappedName = name {
    print("Hello, \(unwrappedName)")  // Prints "Hello, Alice"
} else {
    print("No name provided")
}

In this case, if name contains a value, it's assigned to unwrappedName, which can be used safely within the block. If name is nil, the else block runs.

### Why not just force unwrap?
You could force unwrap an optional using !, but if the value is nil, it will cause a crash:

var name: String? = nil
print(name!)  // Causes a runtime crash
//Optional binding avoids this issue by checking first.

### Providing a Fallback Value
Another way to handle a missing value is to supply a default value using the nil-coalescing operator (??). If the optional on the left of the ?? isn’t nil, that value is unwrapped and used. Otherwise, the value on the right of ?? is used. For example, the code below greets someone by name if one is specified, and uses a generic greeting when the name is nil.
let name: String? = nil
let greeting = "Hello, " + (name ?? "friend") + "!"
print(greeting)
// Prints "Hello, friend!"

### Force unwrapping
 in Swift is a way to directly access the value of an optional. You do this using the ! operator. It tells Swift, "I'm sure this optional has a value, so unwrap it now."
 However, if the optional is nil and you try to force unwrap it, your app will crash.

Why would you use force unwrapping?
You might use force unwrapping if you are absolutely sure that an optional contains a value at a certain point in your code. But because it's risky, you should avoid it unless you're confident that the optional isn't nil.

### Implicitly Unwrapped Optionals













