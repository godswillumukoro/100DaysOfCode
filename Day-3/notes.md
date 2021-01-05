## DAY 3:

05-01-2021

Learning to use the programming language called C. It a different programming langugae from scratch because its text-based. But ut still contains all the main feature of the formaer language learnt like:

- function
- condition
- Boolean expressions
- loops

Guides to Writing good code:

1. Correctness: Does it work as intended?
2. Design: How well written your code is (DRY, efficient)
3. Style: Makes your code more readable. More like aesthetic eg. in essay → punctuation, indentation.

Computer speak machine code(binary, zeros and ones)

Humans use source code to tell the computer what to do. This source code then gets converted into machine code. Source code refers to code that does something irrespective of the programming language.

Compiler: Program designed to convert source code to machine code

Source code → Compiler → Machine code

How to compile a program in c:

using the "make" keyword. For example: make hello

How to run a compile c program:

./hello

Functions & Arguments

Functions are like a mini-program. They are actions or verbs that can be used to do something within a program.

Arguments: Functions can take inputs, these are called arguments or parameters.

Side effects vs Returned value

Side effects are results that gets "printed on the screen" for example.

Returned value are results that are handled to you for subsequent use.

Short hand notation

\n (New Line) - Move the cursor to the next line.

%s (Format String) - Formats string

Header Files

Header files gives you a bit more functionality than what you get out of the box from the c programming language. Just like extensions in scratch, Header files are code that have ben writen by other programmers which you can import into your code. and get to do things alot more easier and quicker.

stdio.h - Standard Input Output dot H (.h - header file) : This is a popular file that enables you get input ad output from the user. 

cs50.h - Code written by the cs50 instructors to make doing some tasks during the course much easily.

cs50 Command Line Tools

help50: Translates error messages into more human understandable messages.

style50: Help indents your code and makes it more stylish.

check50: Helps check the correctness of the code. Written automated tests that are consistent with whatever the homework is.

Command Line Shortcuts

1. li - list
2. rm - remove file
3. mv - mv hello.c goodbye.c : renames hello to goodbye
4. mkdir - make directory
5. mv - move: mv hello.c lecture (Moves hello to lecture directory
6. cd - change directory
7. .. - parent directory (mv hello.c ..)
8. rmdir - remove a directory (rmdir lecture/)
9. ./ - refers to current directory
10. cp - copy
- - When you see * it means that its an executable file (eg. hello*)

**Integer**: Supports both positive and negative numbers. Max 32 bits. It can accept a max of 4 billion numbers, this max size is shared between the negative an positive counter parts, so, ints in c can only have 2 billion positive numbers and 2 billion negative number to give a total of 4 billion numbers.

**Long**:  Max 64 bits.

**TYPECAST**

Conversion from one data type to another fi it makes mathematical sense. For example

float z = (float) x / (float) y

Here, the integers x and y are been typecast into floating point numbers.

### Conditions

if

if else

(|| or && and)

### Loops

**While Loop**

```css
int i = 0;
    
    while(i<3)
    {
        printf("%s", "meow!!!\n");
        i++;
   
```

**For Loop**

```css
for(int i = 0; i<3; i++){
        printf("%s", "meow!!!\n");
    }
```

1. Initialize any variable to a value. - int i = 0;
2. Condition, you want to check again and again - i < 50
3. Update: incrementation or decrementation. - i++

**Do While Loop**

Do Something one time first, while (comes after the program has done something once) this condition is true.

```css
do
{
		n = get_int("Type a positive number: ");
}
while (n < 1);
```

### Prototype

A hint. A clever way of telling the compiler "there will exist this particular function, but just not now." This way, the compiler will not run into bugs if it has to parse the function even before it gets compiled y the default top to bottom method. 

### Return Value

A way the computer returns a value back to to the programmer after doing some computations.

**return** keyword is used.

### Input and Output inside a function

```css
int get_positive_int(void)

{

...

}
```

Here, the input is **void** and the output is **int**.

### Scope

The scope of a variable is the lines of code in which it exists and where you can use that variable. It simply no longer exists outside the walls of the curly braces in which it was created.
