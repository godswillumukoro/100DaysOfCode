## DAY 6:

10-01-2021

Continued WEEK2 - ARRAYS

To check for null in a for-loop:

```css
for(int i = 0; s[i] != '\0'; i++)
    {
        printf("%c", s[i]);
    }
```

Alternatively:

```css
for(int i = 0, n = strlen(s); i < n; i++)
    {
        printf("%c", s[i]);
    }

//make sure to include <string.h> first.
```

### Exit Status

Numbers returned in code by the programmer denoting a special meaning (eg. error 404)

```css
int main(int argc, string argv[])
{
    if(argc != 2)
    {
        printf("missing command-line argument\n");
        return 1;
    }
    printf("hello, %s\n", argv[1]);
    return 0;
}
```

The returned numers (exit status) can be accessed from the cli using:

```css
echo $?
```

### Cryptogrphy

The art of scrambling or hiding information.

**Mutating Texts:**

We need as input: **plain text**, an algorithm to scramble the text, this algorithm is called **cipher**, and the output, which is the scrambled text is called **cipher-text**. You also need a **secret key** as input ****that describes the way the input plain text will be ciphered and that would also be the key to deciphering the information the other way round.
