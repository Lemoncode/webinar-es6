# Closure

A closure is an inner function that has access to the outer (enclosing) function’s variables—scope chain. The closure has three scope chains: it has access to its own scope (variables defined between its curly brackets), it has access to the outer function’s variables, and it has access to the global variables.

http://javascriptissexy.com/understand-javascript-closures-with-ease/

# Steps

You create a closure by adding a function inside another function.

Our objective it's to freeze a time snapshot. Lets start by writing a functionm that tries
that without clsure structure.

Every time we call this function we have a different value.

```javascript
function getTime() {
   const date = Date.now();
   return date;
};

console.log(getTime());

setTimeout(function (){
  console.log(getTime());
}, 500);
```

Let's applied a closure and see what happens now. Now the time snapshot reminds
even after we call teh function after a period of time.

```javascript
function getTime () {
   const date = Date.now();
   return function () {
     return date;
   }
};

const freeze = getTime();

console.log(freeze());
setTimeout(function () {
  console.log(freeze());
}, 500);
```

Even closure is not a new future of JavaScript is the startting point to achieve
patterns, such as reveal pattern. When we use bundling technologies that supports
ES6 modules, behind the scenes they use pattern like reveling pattern whic base
is the clousure.
