## Introduction
Javascript is a multi-paradigm, event driven programming language which was first introduced on December 4th 1995.  
It's popularity grew as the internet exploded into the mainstream and as of 2022 approximately 98% of websites worldwide use Javascript in some capacity.

## Syntax
Javascript has 3 common keywords for variable declaration:
```js
let x=5;
var y=6;
const z=7;
```
The following table shows the differences between these variable declarations:
|  | Can redeclare variable | Can update variable data | Scoping Rule |
|---|---|---|---|
| var | Yes | Yes | Global/Function |
| let | No | Yes | Block |
| const | No | No | Block |

var declarations can sometimes lead to erroneous behavior as subsequent declarations will likely override the global variable. For example:
```js
var greet = "Hi";
if (true) {
    var greet = "Hello"; 
}
console.log(greeter); // "Hello"
```
The other two do not have this issue and nowadays it is preferable for variables to be declared using let as variable shadowing works much better

As the code example displays JavaScript uses parentheses and brackets for block declarations.
Furthermore JS supports the following primitive data types:
Null,Undefined,Boolean,Number,BigInt,String,Symbol.  
For the most part many people will personally use String, Numbers and Booleans extensively. And dealing with undefined which often presents itself when there is an issue with the code. As well as using common things like arrays and dictionarys should the need arise.

## Data Structures and Uses
Speaking of arrays and dictionaries, everything in JavaScript is an object. Arrays are dynamic objects which allows you to give it new properties which you can access however you wish. While dictionaries present a way to map a key-value pair.
They are defined like following:
```js
let arr=[];
let dict={};
```
While these are useful, these do not robustly encapsulate all we may need. To which we turn to the greatly flexible object.  
By defining our own data structures we can do anything we may need. Stacks, Queues, Linked Lists, Sets, HashMaps etc...
These can be defined by using object-oriented programming or functional means
```js
class Stack(){
  //Possibly we may internally store the stack as an array
  constructor();
  //Methods below;
}
```
Functional example
```js
function Stack() {
  this.count = 0;
  this.storage = {};

  this.push = function (value) {
    this.storage[this.count] = value;
    this.count++;
  }

  this.pop = function () {
    if (this.count === 0) {
      return undefined;
    }
    this.count--;
    var result = this.storage[this.count];
    delete this.storage[this.count];
    return result;

  }
  this.peek = function () {
    return this.storage[this.count - 1];
  } 
  this.size = function () {
    return this.count;
  }
}
```
This example can really show how flexible JavaScript is, compared to languages like Java, C# or similarly python. JS is a language who's passing around of functions is really common place.  
Entire web frameworks are build upon defining reactions to user interactions in the form of JS functions and back end calls.
## Paradigms
Like mentioned before JavaScript is fundamentally object-oriented, but allows for easy functional programming (whilst not recommended)  
As it is interpreted, it also consequently follows imperative and procedural doctrines. Where code is focused on defining a set of instructions to achieve a wanted result.  
The nice thing about the loose nature of JavaScript is similar to python, it is easy to write simple code and to learn. Whether someone from a functional or object-oriented background wishes to learn, JavaScript has known avenues to ease the journey.

## Comments
That being said, I personally do not enjoy JavaScript for similar reasons I do not enjoy python.
I have a firm belief that strongly typed languages are better in the long run for any project which means to grow.  
JavaScript has a Typed version which then 'compiles' down to JS called TypeScript. It helps making sure there is no 'hacky' code being written.  
Despite this I am not blind, JavaScript is successful because of it's intense flexibility and is the driving force for how we can have more than just plain text web pages. But given the choice I would rather keep something like C#.

A great meme on reddit once summed it up pretty well:
![image](https://user-images.githubusercontent.com/55760411/219215491-0f2aa972-6df7-426b-b7e6-5af908c90524.png)


<details><summary>Glossary</summary>
<p>
<b>Dynamic Typing</b>: The process where an interpreter will only assign a variable's type at runtime based on the variable's value at the time
  
<b>Weak Typing</b>: The process where a programming language does not strictly enforce type parity for operations and may lead to implicit conversions between types as the code runs.  
As opposed to strongly typed languages which require explicit type equality or (often) explicit type casting.
  
<b>Variable Shadowing</b>: When a variable is named the same like another in an outer scope referencing the outer and this new variable. [Wiki on shadowing](https://en.wikipedia.org/wiki/Variable_shadowing)
</p>
</details>
