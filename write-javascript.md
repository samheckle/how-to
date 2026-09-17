# How to: Write JavaScript Cheatsheet

This is a quick reference for writing basic JavaScript code. Many of the references provided have relevant p5.js explanations. Although typically JavaScript does not have a visual component, p5.js is often a starting point for learning the syntax of JavaScript and has tons of tutorials that detail the concepts here. 
## Comment

These are notes embedded inside the code. These are ignored by the computer and designed for developers to write about specific parts of the code. 

```js
// double slash is a comment in javascript
// for quick commenting, use hotkeys
// ⌘ + / (Mac)
// CTRL + / (PC)
```

We can also write multiline comments:

```js
/* 
this is a comment that spans a lot of lines
usually we only want comments to be like 60-80 characters long
*/
```

Helpful review on code comments: 
- MDN Code Style Guide: [Writing Comments](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Code_style_guide/JavaScript#comments) 
- Coding Train: [writing comments in p5.js](https://thecodingtrain.com/tracks/code-programming-with-p5-js/code/1-intro/6-comments)

---
## Data Types and Variables

JavaScript variables can hold the following data types:

- Number
- String
- Boolean
- Array
- Object

A variable is a named piece of code that holds some data. We make a variable by "declaring" it. We give a value to a variable by "assigning" the variable name a value with a single `=`

```js
// variable declaration using let
let myVariable 
// variable declaration (let) and assignment (=)
let mySecondVariable = 7 
```

### Number

In JavaScript, there are only one type of numbers. So we don't distinguish between with or without decimals, they are all *Number*

```js
let whole = 15 // no decimals
let decimal = 40.6 // with decimals
```

###  String

A string is a list of characters, wrapped in `""` or `''`. It doesn't matter if it is single or double quotes.

```js
let sentence = "This uses double quotes"
let line = 'This uses single quotes. Both are strings.'
```

#### String concatenation and literals

Concatenation is adding two strings together.

```js
let poem = "You may write me down in history"
let line = "With your bitter, twisted lies"

// No space between lines
poem + line // You may write me down in historyWith your bitter, twisted lies

// Add a space
poem + " " + line // You may write me down in history With your bitter, twisted lies
```

String literal uses \`\` (backtick) and `${}` to fill in variables inside a string:

```js
let name = "Sam"

let greeting = `Hi ${name}!`
```
### Boolean

Booleans can only hold two values: `true` or `false`

```js
let isDay = true
let isNight = false
```

Helpful review on basic data types:
- Coding Train: [Variables](https://thecodingtrain.com/tracks/code-programming-with-p5-js/code/2-variables/2-define-variables)
- Coding Train: [Incrementing](https://thecodingtrain.com/tracks/code-programming-with-p5-js/code/2-variables/3-incrementation)
- p5.js Tutorial Blog: [Variables and Change](https://p5js.org/tutorials/variables-and-change/)
### Array

Array is a list of data written with square brackets. Arrays are living variables, so you can change the value of them over time. 

```js
// you can initialize an array without any data because you can add data later
let emptyArray = []
// you can also initialize with data and comma separated values
let animals = ["Cat", "Dog", "Giraffe"] // array of strings
let evenNumbers = [2, 4, 6] // array of numbers
```

To access elements in an array, we use the array name + `[]`. Inside the `[]`, we put the index, or the address of the element we want to retrieve. The index can be calculated by starting at 0. You can think of it as the distance from the first item.

```js
let animals = ["Cat", "Dog", "Giraffe"]

animals[0] // "Cat"
animals[1] // "Dog"
animals[2] // "Giraffe"
```

Arrays have properties that can give us information of them. In order to access a property, we need to use the array name + `.` + the property we are trying to access. 

A common and useful property is `.length`

```js
let animals = ["Cat", "Dog", "Giraffe"]
animals.length // count the number of items in the array
```

There are also functions on arrays, which follow the same syntax as a property.

`push()` adds an item to an array:
```js
let animals = ["Cat", "Dog", "Giraffe"]
animals.push("Hamster")

animals // ["Cat", "Dog", "Giraffe", "Hamster"]
```

You can remove items from an array using `splice()`

```js
// splice(start, deleteCount) 
// it takes where you want to start and how many elements you want to remove
let evenNumbers = [2, 4, 6, 8, 10] 
evenNumbers.splice(3, 1) // removes 8
```

Helpful review on arrays:
- Coding Train: [Arrays](https://thecodingtrain.com/tracks/code-programming-with-p5-js/code/7-arrays/1-arrays)
### Objects

Object is a data structure written with curly braces. Objects syntax is written as key: value pairs. 

```js
let pet = {
	name: "Oreo",
	age: 7, 
	isDog: false
}
```

We could access items in the object by using `[]`, or we can use the `.` syntax.

```js
pet.name // "Oreo"
pet["age"] // 7
```

We can also dynamically add to the object by creating a new property:

```
pet.isCat = true
```

Helpful review on objects:
- javascript.info: [Objects](https://javascript.info/object)
- p5.js Tutorial Blog: [Data Structure Garden](https://p5js.org/tutorials/data-structure-garden/)
### Casting

Casting refers to converting one data type to another.

```js
let num = 15

num.toString() // converts to "15", instead of 15

let numberWord = "15"
let wordFromNumber = parseInt(numberWord) // converts to 15, instead of "15"
```

This is useful when requesting data from somewhere else and needing it to be in a specific format.

---
## Comparisons

`if` statements allow for specific code blocks to be triggered

```js
let name = "Sam"

if(name == "Sam"){
	console.log("Sam is the name")
}
```

We use comparison operators, such as `==`, `>`, `<`. There is a difference between `=` and `==`!

`if` statements can only handle one expression at a time, so we use logical operators to do more than one expression: `&&`, `||`, `!`

```js
let num = 10

5 < num < 15 // syntax error, more than one expression
5 < num && num < 15 // correct syntax, using &&
```

`&&` allows us to check if both expressions are true

```js
let awake = true
let atSchool = true

if(awake == true){
	alert("i'm awake")
}

if(awake && atSchool){
	alert("learning~")
}
```

`||` allows us to check if *one* side of the expression is true

```js
let hasCoffee = false
let hasTea = true

if(hasCoffee || hasTea){
	alert("increased caffeine intake")
}
```

`!` negates, or does the opposite

```js
let awake = false
let atSchool = true

// awake = false; !awake = true
if(!awake){ 
	alert("asleep")
}

if(!awake && atSchool){
	alert("behind the vending machine?")
}
```

We can also cascade `if` statements by checking each step of the way. If any of the conditionals evaluates to `true`, it executes that code block and skips the rest.

```js
let hasCoffee = false;
let hasTea = false;
let isWeekend = true;

if(hasCoffee || hasTea){
	console.log('awake!')
} else if (isWeekend){
	console.log('sleeping in')
} else {
	console.log('zzz')
}
```

Helpful review on `if` statements:
- Coding Train: [Conditionals](https://thecodingtrain.com/tracks/code-programming-with-p5-js/code/3-conditionals/1-conditionals)
- Coding Train: [`if`, `else if`, and `else`](https://thecodingtrain.com/tracks/code-programming-with-p5-js/code/3-conditionals/3-else-if-and-or)
- p5.js Tutorial Blog: [Conditionals and Interactivity](https://p5js.org/tutorials/conditionals-and-interactivity/)

--- 
## Functions

A function is a specific action in code. 
### Built-in Functions

Some helpful built-in functions, which are functions that are native to JavaScript.

One such function is `console.log()`. When writing front-end javascript, we can open the console via the "Inspector" `Right Click Webpage → Inspect`. 

```js
let teacher = "Sam"
console.log(teacher) // prints "Sam" to the console
```

Another is `alert()`, which prompts an alert on the screen:

```js
alert('Hello!')
```
### Custom Functions

In JavaScript, there are three ways to declare a function:

```js
// function declaration
function hi(){}

// function expression
let hello = function () {}

// arrow function
let greetings = () => {}

// call the functions
hi()
hello()
greetings()
```

If we use variables to store the function, they need to happen *after* the variable is created. 

```js
hello() // this errors

// function expression
let hello = function () {}

hello() // this works
```

Functions can accept parameters, which are values passed into the `()`.

```js
function myPet(name, age, type){
	console.log(`${name} is a ${age} year(s) old ${type}`)
}

myPet("Saffron", 13, "cat") // Saffron is a 13 year(s) old cat
```

But, functions can also accept *functions* as parameters, known as **callbacks**. Generally, we use built-in functions that have callbacks, and we use an anonymous arrow function.

```js
// parameter 1: '/test'
// parameter 2: anonymous callback function
app.get('/test', ()=>{})
```

Helpful review on functions:
- Coding Train: [Function Basics](https://thecodingtrain.com/tracks/code-programming-with-p5-js/code/5-functions/1-basics)
- Coding Train: [Function Parameters](https://thecodingtrain.com/tracks/code-programming-with-p5-js/code/5-functions/2-arguments)
- p5.js Tutorial Blog: [Organizing Code with Functions](https://p5js.org/tutorials/organizing-code-with-functions/)

---
## Loops

```js
let friends = ["Trey", "Natasha", "Emma", "Nathan", "Lulu"]

// forward loop
for(let i = 0; i < friends.length; i++){
	console.log("Hi " + friends[i])
} 

// backward loop
for(let i = friends.length - 1; i >= 0; i--){
	console.log("Hi " + friends[i])
}
```

We could also use a shorthand `for-of` loop instead of using the index `i`

```js
let friends = ["Trey", "Natasha", "Emma", "Nathan", "Lulu"]

for(let name of friends){
	console.log("Hi " + name)
}
```

Helpful review on loops:
- Coding Train: [Loops](https://thecodingtrain.com/tracks/code-programming-with-p5-js/code/4-loops/1-while-for)
- Coding Train: [Arrays and Loops](https://thecodingtrain.com/tracks/code-programming-with-p5-js/code/7-arrays/2-arrays-loops)
- Coding Train: [Arrays of Objects](https://thecodingtrain.com/tracks/code-programming-with-p5-js/code/7-arrays/3-arrays-objects)
- p5.js Tutorial Blog: [Repeating with Loops](https://p5js.org/tutorials/repeating-with-loops/)