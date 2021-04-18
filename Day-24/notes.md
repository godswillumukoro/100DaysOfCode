## DAY 24:

02-02-2021 [Here's the tweet](https://twitter.com/umuks_/status/1356689386969120772?s=20)

Continuing  Lecture 7 - SQL

## Lambda Functions

A Lambda function is an anonymous function. Typically used when you have a one-liner function and you choose to instead pass the value of the function as an argument to another function, instead of passing the name of the function itself. See example below: 

This:

```python
import csv

titles = {}

with open("Favorite TV Shows - Form Responses 1.csv", "r") as file:
    reader = csv.DictReader(file)
    for row in reader:
        title = row["title"].strip().upper()
        if title not in titles:
            titles[title] = 0
        titles[title] += 1
#PAY ATTENTION FROM HERE

def f(title):
    return titles[title]

#iterate over the set to print out only those unique values
for title in sorted(titles, key =f, reverse=True): #the titles values is the type of data structure that you can iterate over. Which it will be if its a list, set or dictionary.
    print(title, titles[title]) #sort by value instead of key
```

Can be written as: 

```python
import csv

titles = {}

with open("Favorite TV Shows - Form Responses 1.csv", "r") as file:
    reader = csv.DictReader(file)
    for row in reader:
        title = row["title"].strip().upper()
        if title not in titles:
            titles[title] = 0
        titles[title] += 1
#PAY ATTENTION FROM HERE, Notice that the function is removed.

#iterate over the set to print out only those unique values
for title in sorted(titles, key =lambda title: titles[title], reverse=True): #the titles values is the type of data structure that you can iterate over. Which it will be if its a list, set or dictionary.
    print(title, titles[title]) #sort by value instead of key
```

## Lets Now Search For a Particular Show and Output the Popularity Thereof

```python
import csv

title = input("Title: ").strip().upper()

with open("Favorite TV Shows - Form Responses 1.csv", "r") as file:
    reader = csv.DictReader(file)
    counter = 0
    for row in reader:
        if row["title"].strip().upper() == title:
            counter += 1
            
print(counter)
```

What are the limitations of this approach?

1. **For Loop** uses BigO(n), which means its iterates one after the other meaning this application will become slow overtime if the data in the database is huge.
2. **Flat File Databases** are quite useful when you want to do something quickly of download data from from a third-party (eg. Google sheets) in a more portable means that can be used by different people and different systems. CSV is as simple as it gets because you do not need to own a large database system/product, its a very simple text file so you can use any text-editing program or any programming language to access it.

    **But Flat FIle Databases aren't the best to use for large scale applications because they don't lend themselves to more efficient queries. At best you have to search top to bottom, left to right.**

    There are better databases for solve this, konwn as **Relational Databases**.

# Relational Databases

Instead of being files where you store data, RD are programs where you store data. These programs use a lot of memory (RAM) where they store data and they persist data (keep it long term) by storing your data also  in files.

They give us more feature and they use more data structures so we can search for, insert, update, delete data much more efficiently than we could when using just CSV files.

## SQLite

RD use **tables** as opposed to using **sheets** (Spreadsheets in CSV).

SQLite store all your data into a binary file (0s and 1s). To interact with that binary file, wherein all of your data is stored, we need some kind of user facing program - **sqlite3**

SQL is a language used to query data stored in a Relational Dataases.

What you can accomplish simply balls down to:

C R U D

Create

Read 

Update

Delete

But in SQL these are the commands to achieve the above functionalities:

CREATE, INSERT

SELECT

UPDATE

DELETE

### How to use SQL on Mac

Once you have opened terminal, you can import an existing CSV file by first cd into the directory where the file exists, then use the following commands:

```sql
sqlite3
.mode csv
.import 'file-path-directory' schemaname;
.schema
```

### Some SQL Commands

```sql
SELECT DISTINCT(title) FROM shows;
```

Filters and display only non-duplicate values.

```sql
SELECT * FROM shows
```

Displays all data in the shows schema

```sql
SELECT title, genres FROM shows
```

Displays two columns from the schema, namely, title and genres

### Writing Code to Load Our Data into SQL

While **.import** might be useful to quickly import data in csv files into SQL, it might not always be the best apporach.
