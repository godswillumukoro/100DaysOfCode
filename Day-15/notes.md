## DAY 15:

19-01-2021 [Here's the tweet](https://twitter.com/umuks_/status/1351766339254448137?s=20)

Continued Lecture 4 - Memory

Started Lecture 5 - Data Structures

### Recursion

A recursive function is one that calls itself. See example below:

**original code:**

```css
void draw(int h);

int main(void)
{
    int height = get_int("Height: ");
    draw(height);
    
}

void draw(int h)
{
    for (int i = 1; i<= h; i++)
    {
        for (int j = 1; j<=i; j++)
        
        {
            printf("#");
        }
        printf("\n");
    }
}
```

**recursive code:**

```css
void draw(int h);

int main(void)
{
    int height = get_int("Height: ");
    draw(height);
    
}

void draw(int h)
{
    if (h == 0)
    {
        return;
    }
    
    draw(h - 1);
    for (int i=0; i < h; i++)
    {
        printf("#");
    }
    printf("\n");
}
```

### Iteration vs Recursion

Iteration will always work, when using the iterative version, I will never overflow the stack. 

The recursive version is a cool powerful way of doing things, but there iis a danger, you might finitely touch memory you shouldn't.

### Buffer Overflow

A chunk of memory that you can use as you see fit. Buffer overflow means going beyond the boundaries of that array.

Is when you allocate an array, and go too far past the end of it. Or you use malloc and nonetheless, go farther than the chunk of allocated memory.

## Taking off the Training Wheels

All of these functions in the CS50 library can be implemented with other C functions that weren't from CS50, using one like **scanf.**

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e04a45ca-5f87-4375-ad68-c6d9697ce181/Screenshot_2021-01-19_at_04.45.21.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e04a45ca-5f87-4375-ad68-c6d9697ce181/Screenshot_2021-01-19_at_04.45.21.png)

See example below demonstrating how to use **scanf** in code

```css
int main(void)
{
    int x;
    printf("x: ");
    scanf("%i", &x); //takes a scan from a user's keyboard, int, and stores it in the location of x.
    printf("x: %i\n", x);
}
```

The problem with this "**get_int"** is that there is no error checking, it just returns 0 if the use has passed the wrong value in.

See custom example of custom "**get_srtring**" below:

```css
char s[4]; //Gives 4 bytes from the stack and not heap because we are not using malloc 
    printf("s: ");
    scanf("%s", s); //no need for &s because s is an address
    printf("s: %s\n", s);
```

The problem: Non-dymnamic. If the user were to pass over 4 characters, the program may behave abnormally or crash even.

When get_string from cs50 was doing is, get_string calls malloc for you, and it calls. it for as big a chunk of memory as the string passed in by the user.

## File IO

Lets's create a program that will ask the user for a **name** and **number** and then go ahead and write them to a file

```css
FILE *file = fopen("phonebook.csv", "a");
    if (file == NULL)
    {
        return 1;
    }
    
    char *name = get_string("Name: ");
    char *number = get_string("Number: ");
    
    fprintf(file, "%s,%s\n", name, number);//prints to a file
    
    fclose(file); 
```

# Data Structures

In C, arrays arem't easily resizeable, so you you decide to resize an array in the future, maybe because the program is running long enough where you need to store more values in it, **you are kind of in a bind.**

Bytes un the computer's memory might very well be in use by other variables or aspects of your program. 

The solution: Copy the old array into the new array with the size that you want.

## Linked List

A data structure that solves some of the problems in an arrray.
