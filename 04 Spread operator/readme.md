# spread operator

The spread syntax allows an expression to be expanded in places where multiple arguments (for function calls) or multiple elements (for array literals) or multiple variables (for destructuring assignment) are expected.

## 01 For functions

[Demo](https://codepen.io/daniel-sanchez/pen/XaOGmq);

```javascript
const displayAllFruits = function (...fruits) {
  fruits.forEach((fruit) => console.log(fruit));
};

displayAllFruits('banana', 'apple', 'orange');

// "banana"
// "apple"
// "orange"
```

## 02 For arrays

[Demo adding new item](https://codepen.io/daniel-sanchez/pen/mMvoRJ)

```javascript
const fruits = ['banana', 'orange', 'apple'];
const lemon = 'lemon';
const newFruits = fruits.slice();
newFruits.push(lemon);

console.log(fruits);
// ["banana", "orange", "apple"]

console.log(newFruits);
// ["banana", "orange", "apple", "lemon"]

const colors = ['red', 'black', 'orange'];
const white = 'white';

console.log([...colors, white]);
["red", "black", "orange", "white"]
```

[Demon concat arrays](https://codepen.io/daniel-sanchez/pen/XaOGpB?editors=1112)

```javascript
const fruits = ['banana', 'orange', 'apple'];
const colors = ['red', 'black', 'orange'];

console.log(fruits.concat(colors));
// ["banana", "orange", "apple", "red", "black", "orange"]

console.log([...fruits, ...colors]);
// ["banana", "orange", "apple", "red", "black", "orange"]
```

## For objects

[Demo](https://codepen.io/daniel-sanchez/pen/mMvovr);


```javascript
const johnDoe = {
  name: 'John',
  lastname: 'Doe',
  city: 'London',
};

const janeDoe = Object.assign({}, johnDoe, {
  name: 'Jane',
});

console.log(johnDoe);
// Object {
//  city: "London",
//  lastname: "Doe",
//  name: "John"
//}

console.log(janeDoe);
// Object {
//  city: "London",
//  lastname: "Doe",
//  name: "Jane"
//}

const robertDoe = {
  ...johnDoe,
  name: 'Robert',
};

console.log(robertDoe);
// Object {
//  city: "London",
//  lastname: "Doe",
//  name: "Robert"
//}
```
