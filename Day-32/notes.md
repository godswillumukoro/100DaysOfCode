NOT (!)

Operates one a single expression. !expression returns true if the expression is false. 

```jsx
let flavor = 'watermelon';
if (flavour !== 'grape' && flavor !== 'cherry') {
	console.log('Not available!');
}
```

### Operator Precedence

NOT (!) has higher precedence than && and ||

&& has higher precedence than ||

But parenthesis will change the order of preference. 

```jsx
let x = 7;
(x === 7 || x === 3) && x > 10
```

### Switch Statements

```jsx
let emoji = 'heart';

switch (emoji) {
	case 'sad face':
	case 'happy face':
		console.log('yellow');
		break;
	case 'eggplant':
		console.log('purple');
		break;
	case 'heart':
	case 'lips':
		console.log('red');
		break;
}
```

Incase no case was found, you can use default to handle any exceptions. But it is not always necessary. 

### Ternary Operator

A shortcut way of taking an if/else and making it one line of code. Its called Ternary because there are three pieces. 

```jsx
let status = 'online';
let color;
if (status === 'offline') {
  color = 'red';
}
else {
  color = 'green';
}
//converting the above code to  Ternary Operator
let color = status === 'offline' ? 'red' : 'green';
```

### Creating Arrays

Arrays and Objects are data ****structures ****because they are **Collections of Data.** 

```jsx
let shoppingList = ['cereal', 'cheese', 'ice'];
```

Modifying Arrays

While Strings aren't mutable, Arrays are. See example below on how to modify arrays:

```jsx
let shoppingList =['Cheddar Cheese', '2% Milk'];

shoppingList[1] = 'Whole Milk';
shoppingList[2] = 'Tuna';
shoppingList[3] = 'Pop Corn';
shoppingList[shoppingList.length] = 'Ice Cream';
shoppingList[shoppingList.length] = 'Sharwarma';
```

### Push and Pop

Push - add to end

Pop - remove from end

Shift - remove from start

Unshift - add to start
