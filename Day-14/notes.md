## DAY 14:

18-01-2021

Continued Lecture 4 - Memory

### VALGRIND

valgrind is a command line keyword that is used to check for errors in code that we can not see.  See error example below:

```css
int main(void)
{
    int *x;
    int *y;
    
    x = malloc(sizeof(int));
    
    *x = 42;
    *y = 13;
    
    y = x;
    *y = 13;
}
```

Here we have a pointer error because we initialize the value of y without first declaring it. This program will compile fine and may work too but its will cause bugs in the future and probably cause the program to crash.

**how to use valgrind?**

```css
valgrind ./memory
```

Poking into memory you shouldn't be touching in the first place is bad and can lead to poterntial bugs or your program crashing. See example below:

```css
int scores[3];
for(int i; i < 3; i++)
{
	printf("%i\n", scores[i]);
}
```

Here the scores array was created, but not giving any values and you tried to loop through so as to print out the values in all three location. W

What gets printed is called **garbage value(s)**. This means the computer will not initialise any of those values for you.

But there is a exception, global variables, if you do not set them are conventionally initialized to 0 or nul for you. However this approach is not recommended.

### The way a program is stored in memory

1. MACHINE CODE
2. GLOBALS
3. HEAP
4. STACK

### Stack Overflow

Refers to the process of calling a function so many times that it overflows the heap. At that point your program will crash.
