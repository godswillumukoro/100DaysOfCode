Date - 14 March, 2021
[Tweet Here](https://twitter.com/umuks_/status/1370892114725322755?s=20)

### Accessing Object Properties

```jsx
const numbers = {
  100 : 'one hundred',
  16 : 'sixteen',
  '76 trombones' : 'great song'
};
```

Using . you can not access objects that starts with a number because they are invalid object naming convention.

```jsx
console.log(numbers.100); //Does not work
console.log(numbers[100]); //Works!
```

### Difference between using Bracket Notation and Dot Notation

1. With Dot notation, you cannot target properties starting with a number or properties that have space in their names. 
2. Bracket notation converts object properties automaticaly to strings, so you can name your properties anything, it will get converted to string anyway so it would work. However, you must reference them in strings when calling them.
3. Variables: Bracket notation lets you have variables and reference the value of the variables as object properties. You cannot achieve this with Dot notation, for it will take the variable name to be a property name. Hence it will look for an object property bearing that name and not a variabe. See example below:

```jsx
const palette = {
    red: '#eb4ddb',
    yellow: '#f9ca24',
    blue: '#30336b',
}

let mysteryColor = 'red';

--> palette(mysteryColor) gives us the value of red --> '#eb4ddb'
```

### Adding and Updating Properties

You can update an existing property or create one if it doesn't exist using the following example:

```jsx
const userReviews = {};

userReviews['queenBee49'] = 4.5;

userReviews.mrSmith78 = 3.5;

userReviews['queenBee49'] += 2;

userReviews.mrSmith78 ++;
```

### Objects are Reference Types

Just like arrays, objects are reference types, meaning all the variable stores is a reference. So we can change whats inside that object/array, we just don't change the reference. We declare objects/arrays using const because we want the reference to remain the same, but the values can come and go.

```jsx
const palette = {
    red : '#eb4d4b'
};

const palette2 = palette;
palette2.green = '#00ff33'
```

### Array/Object Equality

```jsx
{} === {}
false
[] == []
false
```

When Arrays or objects are compared or checked for equality, its not their values that gets compared, but their reference in memory. 

```jsx
const user = {
    username: 'CherryGarcia8',
    email: 'garcia@me.com',
    notification: []
};

if (!user.notification.length) {
    console.log('NO NEW NOTIFICATIONS!');
}
```
