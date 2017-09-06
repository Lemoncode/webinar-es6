# Backticks

Just using the new ES6 backticks to:

  - Display multiline text.
  - Embed variable values into strings (similar to print.format or c# string.format).

  # Steps

- Let's first create a multiline text using an ES6 approach:

```javascript
const myString = 'This is a try to get a long string in several lines' + 
                 'using classic ES5 approach';

console.log(myString);
```

This approach sucks: is prone to errors.

- Now let's do the same using backticks:

```javascript
const myString = `This is a try to get a long string in several lines
                  using classic ES6 backticks`;

console.log(myString);
```

- What if we want to display the value of a variable? we can use _${}_

```javascript
const percentage = 80;
const myString = `Total sales increase: ${percentage} %`;

console.log(myString);
```