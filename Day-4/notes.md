## DAY 4:

06-01-2021
[Here's the tweet](https://twitter.com/umuks_/status/1346901949564788740?s=20)

WEEK2 - ARRAYS

This lecture will focus on diving more deeply into c.

**clang:** program that compiles c programs

```css
clang -o hello hello.c -lcs50
```

clang - compiler

-o : please output the next thing

hello - what you want to output

hello.c - take as input hello.c

-lcs50 : link in the cs50 library 

**Steps involved in Compiling your Code From Source to Machine code**

1. Preprocessing: Takes source code and looks for any line with# symbol. For example #include <stdio.h> then it copies the content of that file into my code. 

    Essentially, the header files that are being included at the top, contains all the prototypes for all the functions that exist in the library so that the compiler knows that those functions exist in the code.

2. Compiling: Take the c code, convert it from source code to assembly code.
3. Assembling: Take the Assembly code and convert it into machine code
4. Linking: Combines all machine code, both your code and included libraries that at this stage have now been converted into machine code. So we now a big blob that collectively represent your program.

### List of Debugging Tools

1. help50
2. style50
3. check50
4. printf
5. debug50: A debugger. Lets you seesee the code run  step by step by setting breakpoints

### Debugging

Breakpoints: You can add a breakpoint to where you wish to watch execute step by step.

Call Stack: All the functions that the program has executed and not yet returned from.

### Arrays

A zero indexed list. A sequence of values stored from left to right. It is a variable with one name but contains many (a list of) values. For example:

```css
// Variable
int score1 = 72;
int score2 = 73;
int score3 = 33;

//Array
int scores[3];  //Declaring the array

//Indexing into the array
scores[0] = 72;
scores[1] = 73;
scores[2] = 33;

int scores
[
	0: 73;
	1: 72;
	2: 33;
];              //initializing and assigning
```

The computer needs to know how big the array is when creating it. When passing the array from one function to another, you may leave the array size blank.

```css
int scores[3]; //declaring the array

float average(int length, int array[]); //passing the array into a function as an argument
```
