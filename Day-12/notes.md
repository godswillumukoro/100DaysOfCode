## DAY 12:

16-01-2021

Continued Lecture 4 - Memory

[Here's the tweet](https://twitter.com/umuks_/status/1350575965643153413?s=20)

### Copying Strings

Copying strings as shown in the example below means that the addresses gets coped, hence the copied string is ident5ical to the first. See example below:

```css
char *s = get_string("s: ");
    
    char *t = s;
    
    t[0] = toupper(t[0]);
    
    printf("s: %s\n", s);
    printf("t: %s\n", t);
```
