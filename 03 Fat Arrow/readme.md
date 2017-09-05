# Arrow Functions

Fat Arrow (also known as _Arrow Function Expressions_) is a new ES6 syntax to write **anonymous functions** with bound scope, that means, lexically bound the `this` value.

You can create a new arrow function and store it in a variable:

```js
const greet = (name) => {
  return `Greetings, ${name}!`;
};
const greetings = greet('John');
console.log(greetings); // "Greetings, John!"
```

[Codepen example](https://codepen.io/crsanti/pen/oeOMMm)

You can shorter the expression by removing the curly braces and `return` keyword:

```js
const multiplyBy3 = (num) => num * 3;
const twoByThree = multiplyBy3(2);
console.log(twoByThree);  // 6
```

[Codepen example](https://codepen.io/crsanti/pen/rzbrZd)

Like another anonymous functions with `function` keyword it can be passed to another functions:

```js
const prices = [4, 6, 20, 1, 3, 12, 13, 2];
const total = prices.reduce((total, price) => total + price, 0);
console.log(total); // 61
```

[Codepen example](https://codepen.io/crsanti/pen/KvYBGq)

If the anonymous function accepts only one parameter the braces surrounding the arguments can be ommited:

```js
const names = ['Damien', 'Marc', 'Edward', 'Jane', 'Elsa'];
const firstNameStartingWithE = names.find(name => name.charAt(0) === 'E');
console.log(firstNameStartingWithE);  // "Edward"
```

[Codepen example](https://codepen.io/crsanti/pen/brJjQw)

But if no arguments are defined braces are mandatory.

```js
setTimeout(() => {
  console.log('Executed after one second.');
}, 1000);

[Codepen example](https://codepen.io/crsanti/pen/eEojQV)

// Will output "Executed after one second." after a second.
```

Arrow functions also keeps a cleaner way of handling the current object context:

```js
console.clear();

var car = {
  speed: 0,
  accelerate: function() {
    this.accelerator = setInterval(() => {
      this.speed++;
      console.log(this.speed);
    }, 100);
  },
  cruise: function() {
    clearInterval(this.accelerator);
    console.log('cruising at ' + this.speed + ' mph');
  }
};

car.accelerate();

setTimeout(() => {
  car.cruise();
}, 3000);
```

[Codepen example](https://codepen.io/crsanti/pen/QMPBzp)
