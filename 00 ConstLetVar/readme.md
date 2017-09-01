# Start

Let's get started with Typescript.

We will use Typescript online playground for this demos:

http://www.typescriptlang.org/play/

# Steps

- Let's start with something very basic, if we paste this code on codepen (javascript):

```
let a = 3;
let b = 5;

b= "5";

const result = a + b;

console.log(result);
```

Instead of getting  _8_ as expected result, we will get the following result: _35_

- Let's paste this code into typescript playground and we will notice that we get 
type checking for free.

> Type already infers that _a_ and _b_ vars are typed (number) and throws an error
indicating that the _b_ assignment "5" is wrong.

- We can be more explicit and define the types:

```diff
- let a = 3;
+ let a : number = 3;
- let b = 5;
+ let b : number = 5;

b= 5;

const result = a + b;

console.log(result);
```