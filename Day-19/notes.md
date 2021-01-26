## DAY 19:

26-01-2021

Continued Lecture 5 - Data Structures

## Garbage values are bad in the world of pointers

Any time a variable is created, that does not have an assigned value, it is garbage, and garbage values are bad in the world of pointers. They could lead to "segmentation fault errors" which happens when you accidentally touch memory you shouldn't be touching.

Also initialise the pointer to some value:

```jsx
node *list = NULL;
```

NULL is used to deliberately demonstrate the absence of actual address.

## Leaving Linked Lists

Linked lists are good because they are dynamic, in that we can add/insert values to them. But is still a good amount of work to do if we want to keep them in sorted order. We get the dynamism, but not necessary the performance increase.

## Binary Search Trees

The problem with binary search, is it requires that you use an array so you can have random access.

Linked List is a one-dimensional data structure. ie. from left to right, in the human mind per se.

Binary Search brings the best of both worlds, its a two-dimensional data structure that has not only width, but height. and we can stitch all these values using pointers.

Pointers are like a needle that we can use to stitch things in memory.

![./images/01.png](./images/01.png)

A root node, and left and right children.

Computer scientists use this data structure, in order to have the dynamism of a linked list where you can add more and more nodes to the tree.

### The Pattern

If you pick any node in this tree, its left child will be less than its value and the right child will be greater than its value. Some times the Binary Search Tree might begin to look like a linked list, where its more linear and less logarithmic, in this case you could have some algorithms built into the data structure to shift and balance things up.

For example:

**This:**

```jsx
	1
	 2
	  3
```

**Becomes this:**

```jsx
		2
1        3
```

## Hash Tables

An array of linked lists. Predicated on introducing the idea of **hash functions**.

### Hash Function

Allows us map children deterministically ie. with no randomness involved.

A hash function takes an input eg. some string and returns a number as an output.

## Tries or Prefix Tree

A tree, typically used to store words ie. more sophisticated pieces of data other than just numbers alone.

A tree made up of arrays. ie. each of whose node is an array and each of those arrays, is an array of pointers to other nodes.

It takes constant time find a name in the Try data structure. This constant time is caused by the length of the name that is searched.

The number of other names does not impact the number of steps it takes to search for a particular name. [Please substitute name for strings here].

Cons: Memory and Time inefficient.

## Abstract Data Structures

Implemented with some other data structure. Taking lower level implementation detail and simplifying them higher up.

### Queues

A data structure that have an important property. First in line to get in, first to get out of line.

FIFO stands for First In First Out.

A queue generally has at least two operations associated with it:

1. **enqueue: Get in line, wait.**
2. **dequeue: Been served, get out of line.**

### Stacks

A data structure with the LIFO property.

LIFO stands for Last in, Last out. eg. a stack of clothes, the last on the stack becomes the first to get out.

The two operations they support:

1. push: add a value
2. pop: remove a value

### Dictionaries

A abstract data type that helps you associate **keys** with **values**. Just like a dictionary with words (keys) and their meanings (value).

You look up the values by way of their keys. Like we look up a word definition by way of the word itself.
