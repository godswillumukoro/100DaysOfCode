## DAY 20:

27-01-2021

Started Lecture 6 - Python

## Some Python Syntax

### Concatenating Strings

This:

```jsx
from cs50 import get_string

answer = get_string("What's your name? ")
print("hello " + answer)
```

is also this:

```jsx
from cs50 import get_string

answer = get_string("What's your name? ")
print(f"hello, {answer}")
```

### Incrementing Ints

```jsx
counter = 0 #no need to declare data type - int
counter +=1 #increment counter by one. counter++ does not exist in python.
```

### Conditions

```jsx
if x < y:
	print("x is less than y")
elif x > y:
	print("x is greater than y")
else:
	print("x is equal to y")
```

### Loops

infinite loop:

```jsx
while True:
	print("hello, world")
```

Finite loop

```jsx
i = 0
while i < 3;
	print("hello world")
	i += 1
```

For loop

```jsx
for i in [0,1,2]: //a list. Give me a variable called i and in the first iteration of the loop, set i to 0
	print("hello world")

for i in range(3): //using range, no need to hard code number of iterations.
	print("hello world")
```

## Getting input from the user

Using the input function, you don't have to import any library. It comes with python by default. See code example below: 

```jsx
answer = input("What's your name? ")
print(f"hello, {answer}")
```

Technically, it prompts the user with a phrase, "What's your name?", waits for them to type in a value; as soon as they hit Enter, it returns whatever the human has typed in for you.

Its analogous ro **get_string** in C. It returns ASCII characters and does not perform arithmetic with numbers like **get_int** will.

To solve this, we could implement **typecasting**

```jsx
# Prompt user for x
x = int(input("x: "))

# Prompt user for y
y = int(input("y: "))

# Perform addition
print(x + y)
```

## Prototypes don't exist in Python

Because the notion of prototypes do not exist in python, we do things a little differently. See code example below:

```jsx
def main():  #Defining the main method
        meow(7)
        
        
def meow(n):  #Defining the meow method
    for i in range(n):
        print("meow")
    
    
main() #calling main at the tail end of the code
```

## Do While Loops don't exist in Python

Do while loops are amazing because they prompt the user at least once before the loop begins. 

```jsx
def main():
    get_positive_int()
    

def get_positive_int():
    
    while True:
        n = get_int("Positive Integer: ")
        if n > 0:
            break
    return n
        
    
    
main()
```

## The * Operator is Overloaded

The * operator has been overloaded to support not just multiplication with numbers, but also automatic concatenation with strings.

**This:**

```jsx
for i in range(4):
    print("?", end="")
    
print()
```

**Can be written like this:**

```jsx
print("?" * 4)
```
