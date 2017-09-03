# Currying

Currying is the act of turning a function into a new function that takes slightly fewer arguments, achieving a slightly more specific task.

http://macr.ae/article/es6-and-currying.html

# Steps

Let's start by making a simple function that will sum up two numbers, using currying:

Let's build the sample using normal functions

```javascript
function sum(a) {
  return function second(b) {
    return a + b;
  }
}

console.log(sum(3)(4));
```

Let's build the same using fat arrow:

```javascript
const sum = a => b => {
  return a + b;
}

console.log(sum(3)(4));
```

We could use currying when e.g. we need to inform about a given parameter on a standard event class.

Pseudocode:

```
onClick (color) => (e) {
   props.setColor(color);
}


<input 
  onclick="onClick('red')"
/>

<input
  onclick="onClick('green')"
/>


<input
  onclick="onClick('blue')"
/>

```