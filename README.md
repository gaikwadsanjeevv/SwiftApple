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













