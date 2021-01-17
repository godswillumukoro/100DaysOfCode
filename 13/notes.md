## DAY 13:

17-01-2021

**Continuing my notes from where i stopped yesterday.**

The result:

```css
//Presuming the user typed "Hi" (without the brackets) when prompted

"Hi"
"Hi"
```

But why? you may wonder. Why did the variable get capitalised when we directly targeted the variable t.

The answer: All we did was copy s into t. And because s is literally just an address in memory, it means what we did was we copied the memory address of s into t. So we are changing one string that is stored in the address s and t both share.

### What is the right way to copy a String?

 1. Create a new memory for variable t.

This we can do by using a special function called malloc (Memory Allocation) that takes as input a number that represents how many bytes of memory  you want to ask the computer for. To use remember to include <stdlib.h>**.** See example below:

```css
#include <stdlib.h>

//Not dynamic
char *s = get_string("s: ");
char *t = malloc(4);

//Recommended
char *s = get_string("s: ");
char *t = malloc(strlen(s) +1); //give me as many characters as there are in s plus 1.
```

**why do we need to +1?**

**The answer:** For the null character.

2. Copy one string into the other

```css
char *s = get_string("s: ");
char *t = malloc(strlen(s) +1); //give me as many characters as there are in s plus 1.

//copying
for(int i = 0, n = strlen(s); i <= n; i++)
{
	t[i] = s[i];
}

t[0].toupper(t[0]);
printf("s: %s\n", s);
printf("t: %s\n", t);

free(t); //frees the computer memory that was used up by malloc so the computer does not run out of memory eventually.
```

3. Check for potential errors and handle them

```css
char *s = get_string("s: ");
char *t = malloc(strlen(s) +1); //give me as many characters as there are in s plus 1.

//error checking for t memory allocation
if (t == NULL)
{
	return 1;
} 

//copying
for(int i = 0, n = strlen(s); i <= n; i++)
{
	t[i] = s[i];
}

//error checking
if (strlen(t) > 0)
{
	t[0].toupper(t[0]);
}
printf("s: %s\n", s);
printf("t: %s\n", t);

free(t); //frees the computer memory that was used up by malloc so the computer does not run out of memory eventually.
```

NULL represents the annul character. It is the absence of an address. Technically, its address 0. And it is different from **/0** thats used to indicate the end of a memory address. 

4, Free up the computer memory that was used up by malloc so the computer does not run out of memory eventually or so that that memory can be reused for something else.

```css
free(t); //frees the computer memory that was used up by malloc so the computer does not run out of memory eventually.
```

### What does all that mean?

1. **NULL** is used for **pointers.**
2. **/0 (nul)** is used for **characters.**
3. There is a function that does all that work for us: **strcpy**

```css
strcpy(t, s);
free(t);
```

**strcpy** takes two arguments: the destination followed by the source and it will just handle all of looping and all for us.
