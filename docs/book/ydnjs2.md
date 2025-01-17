---
layout: default
title: You Don't Know JS Edition 2
parent: Book
---

# You Don't Know JS Edition 2

## Table of contents
- [[#Get Started,|Get Started,]]
	- [[#Get Started,#C1: What Is JavaScript?|C1: What Is JavaScript?]]
		- [[#C1: What Is JavaScript?#What's in an Interpretation|What's in an Interpretation]]
	- [[#Get Started,#C2: Surveying JS|C2: Surveying JS]]
		- [[#C2: Surveying JS#Each File is a Program|Each File is a Program]]
- [[#Scope & Closures|Scope & Closures]]
	- [[#Scope & Closures#Ch1 What's the Scope?|Ch1 What's the Scope?]]
		- [[#Ch1 What's the Scope?#Proving|Proving]]
- [[#Objects & Classes|Objects & Classes]]
- [[#Types & Grammar|Types & Grammar]]
- [[#Sync & Async|Sync & Async]]
- [[#ES.Next & Beyond|ES.Next & Beyond]]

---

## Get Started,
[link](https://github.com/getify/You-Dont-Know-JS/blob/2nd-ed/get-started/README.md)
### C1: What Is JavaScript?
#### What's in an Interpretation 
[link](https://github.com/getify/You-Dont-Know-JS/blob/2nd-ed/get-started/ch1.md#whats-in-an-interpretation)
JS is a compiled language.

### C2: Surveying JS
#### Each File is a Program

Each .js standalone file is its own separate program. Because JS **handles error** file by file, one failed file won't effect the operation of other files.

---

## Scope & Closures
[link](https://github.com/getify/You-Dont-Know-JS/blob/2nd-ed/scope-closures/README.md)
### Ch1 What's the Scope?
> But since these functions hold and access variables, they maintain their **original scope** no matter where in the program the functions are eventually executed. This is called **closure**.
###### Proving JS contains two phases: 1. parsing/compilation 2. execution
**Syntax Errors from the Start**
```js
var greeting = "Hello";

console.log(greeting);

greeting = ."Hi";
// SyntaxError: unexpected token .
```
"Hello" is not printed.

**Early Errors**
```js
console.log("Howdy");

saySomething("Hello","Hi");
// Uncaught SyntaxError: Duplicate parameter name not
// allowed in this context

function saySomething(greeting,greeting) {
    "use strict";
    console.log(greeting);
}
```
"Howdy" is not printed. This Duplicate Parameter error only occurred in strict-mode (`"use strict"` line). 
The JS engine know that the function is in strict-mode and throw the error before printing log.
>Again, the only reasonable explanation is that the code must first be _fully_ parsed before any execution occurs.

**Hoisting**
        


---

## Objects & Classes
[link](https://github.com/getify/You-Dont-Know-JS/blob/2nd-ed/objects-classes/README.md)

---

## Types & Grammar
[link](https://github.com/getify/You-Dont-Know-JS/blob/2nd-ed/types-grammar/README.md)

---

## Sync & Async


## ES.Next & Beyond