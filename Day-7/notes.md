## DAY 7:

11-01-2021

Starting WEEK3 - Algorithms

## Algorithms

Computers are methodical or algorithmic. And so, as powerful as computer may be, they can technically only look at one  location in an array at a time. Humans can glance at an information and take it all at once, but the computer can only do this from left - right, right - left, from middle. All these processes are called algorithms

### Running Time

Refers to how long an algorithm takes to run. O(italicized O. Known as Big O notation.) is formally used to describe the running times of an algorithm.


### Notation:

Big O - Refers to upper bound (worst case) notation when comparing the efficiency or inefficiency of an algorithm


Omega Ω - Refers to lower bound (best case) notation when comparing the efficiency or inefficiency of an algorithm


### Linear Search

 Searches conventionally from left to right, or equivalently from right to left.


### Binary Search

Starts search from the middle. But the list your are searching most be sorted serially for this to work out. 


### Difference Between Linear and Binary Search

Binary search is better than linear search because as the list n) gets bigger, binary search would still be a lot faster than linear search, in fact you may not be unable to tell any noticeable difference in the running time of binary search. But linear search gets obviously slow with larger lists to sort.

### Lets represent all of this in code:

```css
//An array of seven numbers
    int numbers[] = {4, 6, 8, 2, 7, 5, 0};
    
    for(int i = 0; i < 7; i++)
    {
        if(numbers[i] == 0)
        {
            printf("Found\n");
            return 1;
        }
    }
    printf("Not found\n");
    return 0;
```

**return 0** means success. And the programs exits at this point. 

**return 1 (or any other value asides 0)** means something went wrong (failed) . 

### How To Use strcmp()

It is used in linear search and is case-sensitive.

String Compare or **strcmp()** compares two strings together and it returns one of three possible values:

1. If the two strings are equal (letter for letter), the function **returns 0**.
2. If the first string comes before the second (less than the second) in ASCII order, the function **returns a negative value.**
3. If the string comes after the second (greater than the second) in ASCII order, the function **returns a positive value**.

. To use it, you need to include the **<string.h>** file. See example below:

```css
string names[] = {"Tola", "Bolu", "Tolu", "Sade", "Onome", "Basira", "Kola"};
    
    for(int i = 0; i < 7; i++)
    {
        if(strcmp(names[i], "Kola") == 0) //comparing if both values are identical
        {
        printf("Name found");
        return 0;
        }
    }
    printf("Name not found");
    return 1;
```
