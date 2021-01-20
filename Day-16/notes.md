## DAY 16:

20-01-2021

Continued  Lecture 5 - Data Structures

## Linked List (cont'd)

A linked list is a more dynamic data structure when compared to arrays. With linked list, you can grow and shrink the data without touching all of the original data.

0x0 or NULL indicate the absence of an address.

A list of numbers that are linked together. Underneath the hood, the links are implemented by way of addresses or pointers.  

Linked list is a collection of nodes connected via pointers.

A node is a structure that stores stuff you care about. in this case, a number and a pointer to another such structure.

Any time we solve a problem in CS and programming in particular, there is always going to be some price paid. eg. Memory vs Time. There is always going to be a cost or some tradeoff. In linked list, you are saving yourself time, but you will be spending more cost on memory.

### Implementing a Linked List

```css
typedef struct node
{
	int number;
	struct node *next;
}
node;
```

### Advantages of Linked List

They can be stored any where in memory, they don't have to be contiguous like arrays. Which means whenever you want to resize it, you don't have to keep allocating and copying more memory. You have the dynamism which is great performance-wise for Large companies with Big data.

### Disadvantages of Linked List

You cannot rely on binary search. Big0(logn) is faster than BigO(n). But that cannot be relied on here.
