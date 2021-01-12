## DAY 8:

12-01-2021

Continued Lecture 3 - Algorithms

[Here's the tweet](https://twitter.com/umuks_/status/1349088809498062848?s=20)

### How To Create Your own Data Type in C

C gives us the ability to create our own custom data types.

**But first why?**

As programmers, we will make mistakes in our code. And the more we can write code that is self-defensive, that protects you from yourself, the better off you're going to be, the more correct your code is going to be, and the more easily you're going to collaborate successfully and real world projects.

Generally, you should not trust yourself or other people with whom you're writing code, you should have enough defensive mechanisms in place.

```css
string names[] = {"Brian", "David"};
    string numbers[] = {"+234-690-0987", "+234-123-5432"};
    
    for(int i = 0; i < 2; i++)
    {
        if(strcmp(names[i], "David") == 0)
        {
            printf("%s", numbers[i]);
            printf("\n");
            return 0;
        }
    }
    printf("Phone number not found!\n");
    return 1;
```

When the list of names or numbers gets long, the odds the someone messes the order up is too high its better to keep related data together.

That's why we sometimes we need our own data types to encapsulate some values. For example a phone book has both name and number. Lets see how we would create our own custom data type for phone book. Check out the format for creating our own data types below:

```css
typedef struct
{
	string name;
	string number;
}
person;
```

**typedef** - This allows you to define a type.

**struct** - Data Structure. We can structure our data type with this. ie. create a composition of multiple data types inside.

**string name and number** - Specifies the data type you want and the names you want to give to those data types.

**person** - The name of the data type that you want to invent. 

**Now lets recreate the array phonebook example using our own custom data type.**

```css
//creating the array
    
    person people[2];
    
    //populating the array --[0] targets the first person in the array
    
    people[0].name = "Brian";
    people[0].number = "+234-818-9191";
    
    people[1].name = "David";
    people[1].number = "+234-045-6789";
    
    
    
    for(int i = 0; i < 2; i++)
    {
        if(strcmp(people[i].name , "School") == 0)
        {
            printf("%s", people[i].number);
            printf("\n");
            return 0;
        }
    }
    printf("Phone number not found!\n");
    return 1;
```

### Selection Sort

This kind of algorithm sorts a list by selecting the smallest elements again and again and once its found each such small element, it just ignores it and keep decreasing each iteration:

n numbers, then, n - 1, then, n - 2, n - 3 and so forth.

**Pseudocode:**

```css
For i from 0 to n - 1
		Find smallest item between i'th item and last item
		Swap smallest item with i'th item
```
