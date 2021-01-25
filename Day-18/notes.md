## DAY 18:

25-01-2021

[Here's the tweet](https://twitter.com/umuks_/status/1353775192380735488?s=20)

Continued Lecture 4 - Data Structures and Algorithms

## Malloc vs Arrays in c

If you create an array using square brackets in c you have painted yourself to a corner, you can't resize that array because it means you are **statically allocating the array on the stack.** Which means you are putting the array into the frame of the computer's memory that belongs to the function's stack frame.

However, if Malloc is used, Memory is allocated from the heap, and that, you can resize.

### Creating an Reallocating an array using Malloc

```jsx
int *list = malloc(3 * sizeof(int)); //using malloc to dynamically allocate the array called list having the size of 3.
   if (list == NULL)
   {
       return 1; //If something bad went wrong, like if I went out of memory all together
   }
   
   list[0] = 1;
   list[1] = 2;
   list[2] = 3;
   
   //This is because malloc allows the use of bracket notation to reference allocated memory becasue its a contiguous chuck of memory like an array is.
   /*
   Or you can write this using pointer arithmetic :
   *list = 1;
   *(list+1) = 2;
   *(list+2) = 3;
   */
   
   //adding a fourth number to this array
   int *tmp = malloc(4 * sizeof(int));
   if (tmp == NULL)
   {
       free(list);
       return 1;
   }
   
   for (int i = 0; i <3; i++)
   {
       tmp[i] = list[i];
   }
   
   tmp[3] = 4;
   
   free(list);
   
   list = tmp;
   
   for (int i=0; i<4; i++)
   {
       printf("%i\n", list[i]);
   }
}
```

### Simplifying things using realloc

```jsx
int *list = malloc(3 * sizeof(int)); //using malloc to dynamically allocate the array called list having the size of 3.
   if (list == NULL)
   {
       return 1; //If something bad went wrong, like if I went out of memory all together
   }
   
   list[0] = 1;
   list[1] = 2;
   list[2] = 3;
   
   //realloc takes two args, first arg = size of memory. second arg = address of already allocated memory
   int *tmp = realloc(list, 4 * sizeof(int));
   if (tmp == NULL)
   {
       free(list);
       return 1;
   }
   
   tmp[3] = 4;
   
   free(list);
   
   list = tmp;
   
   for (int i=0; i<4; i++)
   {
       printf("%i\n", list[i]);
   }
   
   free(list);
```
