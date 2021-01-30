## DAY 22:

29-01-2021

Completed  Lecture 6 - Python

## Writing into Files in Python

This can be done this way:

```jsx
file = open("phonebook.csv", "a")

name = get_string("Name: ")
number = get_string("Number: ")

# Save the name and number to a file
writer = csv.writer(file)

writer.writerow([name, number])

file.close()
```

Can also be implemented this way:

```jsx
with open("phonebook.csv", "a") as file

    name = get_string("Name: ")
    number = get_string("Number: ")
    
    # Save the name and number to a file
    writer = csv.writer(file)
    
    writer.writerow([name, number])
```

## STARTING LECTURE 7 - SQL

## Cons of Flat-File Database

Storing Data as Spreadsheet .CSV files is cool but..

At some point, you might have more data in a spreadsheet than your Mac or PC can handle. If you are building an application that scales, there may be way too much data to use and no one could literally open it on their computer. So we need a solution to that problem of scale.

You can only store static data, you cannot write functions with flat-file datatbase like we do with eg. excel.
