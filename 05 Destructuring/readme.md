# Destructuring

Destructuring is a new ES6 expression that makes it possible to extract data from arrays or objects. Let's see some usage cases:

## Destructuring arrays

```js
const friends = ['James', 'Lisa', 'Paul', 'Mathew', 'Anna', 'Emma'];
const [james, lisa, paul] = friends;
console.log(james); // "James"
console.log(lisa);  // "Lisa"
console.log(paul);  // "Paul"
```

[Codepen example](https://codepen.io/crsanti/pen/MvxMzV)

You can omit values and get values by adding commas between first and last elements in the array:

```js
const friends = ['James', 'Lisa', 'Paul', 'Mathew', 'Anna', 'Emma'];
const [, , paul, , anna] = friends;
console.log(paul); // "Paul"
console.log(anna); // "Anna"
```

[Codepen example](https://codepen.io/crsanti/pen/wqOLNg)

This is also applied for values returned by functions. It works very well with spread operator:

```js
function getFriendsOrderedByConfidence() {
  const friends = ['James', 'Lisa', 'Paul', 'Mathew', 'Anna', 'Emma'];

  return friends;
}

const [bestFriend, ...otherFriends] = getFriendsOrderedByConfidence();
console.log(bestFriend);    // "James"
console.log(otherFriends);  // ["Lisa", "Paul", "Mathew", "Anna", "Emma"]
```

[Codepen example](https://codepen.io/crsanti/pen/zdbVeM)

You can assign default values to variables that might be `undefined`:

```js
function getPeopleInChat() {
  return ['Fay', 'Thomas'];
}
const [person1, person2, person3 = 'Unknown'] = getPeopleInChat();

console.log(person1); // "Fay"
console.log(person2); // "Thomas"
console.log(person3); // "Unknown"
```

[Codepen example](https://codepen.io/crsanti/pen/YxgogP)

With destructuring you can do clever tricks like swapping variables:

```js
let firstElement = 'first';
let secondElement = 'second';

[firstElement, secondElement] = [secondElement, firstElement];

console.log(firstElement); // "second"
console.log(secondElement); // "first"
```

[Codepen example](https://codepen.io/crsanti/pen/RZdzdW)

You can use destructuring in arrays as function parameters:

```js
function saveTodos([firstTask, ...otherTask]) {
  console.log(firstTask);
  console.log(otherTask);
  // Do something with elements
}

const todos = ['Make dinner', 'Call mom', 'Tiddy my room'];
saveTodos(todos);
// Outputs:
// "Make dinner",
// ["Call mom", "Tiddy my room"]
```

[Codepen example](https://codepen.io/crsanti/pen/brZPJW)

## Destructuring objects

You can apply destructuring to objects to create new variables holding object's properties:

```js
const coordinates = {
  latitude: 9.28378173492,
  longitude: -4.29010298412
};
const { latitude, longitude } = coordinates;

console.log(latitude);  // 9.28378173492
console.log(longitude); // -4.29010298412
```

[Codepen example](https://codepen.io/crsanti/pen/wqOLLd)

Notice the variable names are the same as the object ones. This works thanks to _shorter syntax_ for common objects. In other way you can repeat the property name:

```js
const { latitude: latitude, longitude: longitude } = coordinates;
```

You can change the variable names by adding two dots and the new variable name:

```js
const message = {
  s_Author: 'Jack',
  s_Text: 'You are right, Mary!',
  d_Timestamp: 1504553198435,
};

const {
  s_Author: author,
  s_Text: text,
  d_Timestamp: timestamp
} = message;

console.log(author);    // "Jack"
console.log(text);      // "You are right, Mary!"
console.log(timestamp); // 1504553198435
```

[Codepen example](https://codepen.io/crsanti/pen/WEmqBE)

You can extract some object properties returned by functions:

```js
function getUser() {
  // Call some API
  return {
    firstName: 'Rick',
    lastName: 'Williams',
    age: 32,
  };
}

const { firstName, age } = getUser();
console.log(firstName); // "Rick"
console.log(age);       // 32
```

[Codepen example](https://codepen.io/crsanti/pen/GvebVq)

You can apply destructuring to object parameters:

```js
function applyScale({ width, height }, scaleRatio) {
  return {
    width: width * scaleRatio,
    height: height * scaleRatio,
  };
}

const dimensions = { width: 30, height: 45 };
const scaledDimensions = applyScale(dimensions, 2);
console.log(scaledDimensions);  // { "width": 60, "height": 90 }
```

[Codepen example](https://codepen.io/crsanti/pen/QMoXeO)

You can set default values for properties that does not exist:

```js
const dbConfig = {
  host: 'localhost',
  username: 'admin',
  password: 'use@M0r€$oph1st1c@t3dP@$$w0rd'
};

const { host, port = 3000, username, password } = dbConfig;
console.log(host);      // "localhost"
console.log(port);      // 3000
console.log(username);  // "admin"
console.log(password);  // "use@M0r€$oph1st1c@t3dP@$$w0rd"
```

[Codepen example](https://codepen.io/crsanti/pen/EvMBqr)

## Nested destructuring

You can apply deep destructuring for arrays in a more flexible way:

```js
const matrix = [
  [6, 5, 2],
  [4, 6, 4],
  [6, 0, 4]
];

const [firstRow, [secondRowFirstPosition, secondRowSecondPosition], thirdRow] = matrix;

console.log(firstRow);                // [6, 5, 2]
console.log(secondRowFirstPosition);  // 4
console.log(secondRowSecondPosition); // 6
console.log(thirdRow);                // [6, 0, 4]
```

[Codepen example](https://codepen.io/crsanti/pen/GveVKq)

You can do the same with object properties:

```js
const post = {
  id: 122,
  title: 'Looking for some volunteers for a new startup',
  author: {
    id: 192,
    name: 'Alan',
  },
  comments: [],
};

const {
  author: {
    id: authorId,
    name: authorName
  },
  title
} = post;

console.log(authorId);    // 192
console.log(authorName);  // "Alan"
console.log(title);       // "Looking for some volunteers for a new startup"
```

[Codepen example](https://codepen.io/crsanti/pen/WEmVeZ)
