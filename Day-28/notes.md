## DAY 28:

06-02-2020

Started Learning Javascript using :The Modern Javascript Bootcamp Course - Stephen Grider & Colt Steel.

## What is ECMASCRIPT?

There isn't one Javascript installation file that you can download and install, the way we install applications on our computers.

Insteade, JS is implemented by all the different browsers out there, and its up to the browsers to implements the new features.

### ECMA INTERNATIONAL

An organization group that is in charge of all sorts of different standards, not just form programming, for other science fields too including ECMASCRIPT.

### ECMASCRIPT

A set of rules or specification for a programming language. eg. It should have this or that feature. BUT it is not a language in itself, just a document that describes how a language should work.

It is up to the browsers to follow those rules and implement them as JS. It has a community called **TC39** that is in charge of maintaining and evolving the ECMAScript spec.

ES6 - ES2015 (Took about 6 years, from herein, new updates came in yearly)

After ES6, the versions are referred to by their names. For example:

ES2016

ES2017

ES2018

All these terms are referring to the different versions of the ECMASCRIPT specification document.

Because these specification or just text and not a downloadable software, and because all updates are implemented by separate browsers, it means that different different browsers will suport different features at any given point in time.

### JAVASCRIPT

JS is not one language, but a bunch of implementations of different specifications.

### MDN

Mozilla Developer Network is the closest thing we have to an official JS documentation.

## SECTION 1: JS Values & Variables

### Goals

- [ ]  Work with primitive types
- [ ]  Understand let & const
- [ ]  Use String Template Literals
- [ ]  Work with common operators/methods

### 

## Primitive Types

### Numbers

JS has just one **Number** type. Which accepts Positive/Negative/Decimal/Whole numbers etc.

However, because everything is stored in memory, there is a max size for those numbers. So JS does not store an infinitely precise number. For example:

10/3 gives 3.3333333333333335

You might wonder, why is there 5 at the end?

This is because we can't store this irrational number where we have a million infinite threes, so we get an approximation at some point.

### Simple Operations

JS has all the basic math operations you would expect. 

```jsx
//Addition
+

//Subtraction
-

//Multiplication
*

//Modulo
%

//To the power of(Exponents)
**
```

### Standard Order of Operations

In more complicated expressions, different operators get precedence over others.

**PEMDAS:**

Parantheses

Exponents

Multiplication

Division

Addition

Subtraction

### NaN

Stands for Not a Number. It is a numeric value that represents something that is not a number.

Some ways you can arrive at NaN: 

```jsx
0/0 //NaN
1 + NaN //NaN
```

It is used to imply that this is not standard math or Javascript and its going to have a hard time representing this number or this value as a true numeric value. There also are a bunch of other types like NaN:

**Infinity**

**-Infinity**

**0**

**-0**

### Variables

Helps us capture information and remember values.

Variables are like "labeled jars" for a value in JavaScript. We can store a value and give it a name, so that we can:

- recall it
- use it
- or change it later on.

Variables can't have the same name as a JS keyword.

Give variable names that make sense, so you can recall it later when you wish to use it.

It is convention to use **camelCase** when naming variables.

### Unary Operators

Aim to simplify some operations in JS. For example 

```jsx
let score = 10;
//Normal way to reassign the value of a variable
score = score + 5;

//Unary way to do it.
score += 5;
//Note. That also applies to - * /.

//Unary, Happening on one side.
counter++; //adds one to counter, as opposed to:
counter = counter + 1;
counter--; //also can be used to decrement by 1.
counter = counter - 1;
```

### Const

**const** works just like let, except you are not allowed to change the value.

Why would you use const?

- You need an always constant variable to use in your code eg.

```jsx
const pi = 3.14159
```

- Also important when using arrays an object.
- 

### The Legacy of Var

Before let & const, var was the only way of declaring variables. These days, there isn't really a reason to use it.

### Booleans

Booleans are simply true or false values. Yes or No. 1 or 0. ****They are very efficient with regards to the space they take up, since they only take up two values.
