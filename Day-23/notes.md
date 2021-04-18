## DAY 23:

01-02-2021 [Here's the Link](https://twitter.com/umuks_/status/1356286053032882176?s=20)

Continuing  Lecture 7 - SQL

**Writing a quick program that opens up a CSV file, iterates over it, top to bottom and prints out all of the titles. See code example below:** 

```jsx
import csv

# writing a quick program that opens up a CSV file, iterates over it, top to bottom and prints out all of the titles

#open command opens and automaticaally closes the file for me
# "r" means opening the file in read only mode
# as files means we arer giving it a variable name of 
# reader describes what this variable is going to do, could be xyz or anything else. And its going to be the
# return value of calling csv.reader
with open("Favorite TV Shows - Form Responses 1.csv", "r") as file:
    reader = csv.reader(file)
    next(reader) #skip the first role, which contains just the headings
    for row in reader:
        print(row[1]) #index [1] means give me just the title.
```

## Dictionary Readers

Using **csv.reader** isn't the best approach, because you end up having to memorize what number each header represents. And if the file is rearranged or messed up, it will affect the output of your program.

Thats why using the **csv.DictReader** is better because it check for the name as opposed checking for thew numbers. Its still fallible, because if someone changes the name of the header, then your code might break.

**Using DictReader and and sets, lets write a code that displays only uniques titles, not duplicates.** 

```jsx
import csv

titles = set()

with open("Favorite TV Shows - Form Responses 1.csv", "r") as file:
    reader = csv.DictReader(file)
    for row in reader:
        titles.add(row["title"]) #add to the title se the current rows title, and if it already exists there, the set data structure in python will throw away the duplicates for me.
        
#iterate over the set to print out only those unique values
for title in titles: #the titles values is the type of data structure that you can iterate over. Which it will be if its a list, set or dictionary.
    print(title)`
```

**Computers require precise data. But we sometimes make errors when inputing data, whether that's accidentally adding a space after typing in the data. The following code snippet shows how be massage the data by canonicalising (standardising) by uppercasing, then cleaning up all the extra spacing that might have been inputed.** 

```jsx
import csv

titles = set()

with open("Favorite TV Shows - Form Responses 1.csv", "r") as file:
    reader = csv.DictReader(file)
    for row in reader:
        titles.add(row["title"].strip().upper()) #add to the title se the current rows title, and if it already exists there, the set data structure in python will throw away the duplicates for me.
        #strip removes extra spaces to the left or right of the user input. upper converts everthing to upper case.
        
#iterate over the set to print out only those unique values
for title in sorted(titles): #the titles values is the type of data structure that you can iterate over. Which it will be if its a list, set or dictionary.
    print(title)
```

## Using Dictionaries

A Dictionary is just a collection of key, value pairs. Its ability to associate one piece of data to another is a very valuable feature. Now lets refactor the above code to display the frequenncy of movies selected.

Lets make the Title of our shows = KEYS

And the votes of those shows =VALUES of those keys

How to intialize a dictionary: 

```jsx
titles = dict()

# YOU COULD ALSO SAY:

titles = {}
```

## Sorting using sorted()

Sorted() sorts sets by values, lists by values **but** dictionaries by keys therein, but can be overridden by passing a second argument to sorted() called key and it takes its value by name of a function.
