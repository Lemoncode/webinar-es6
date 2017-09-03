# Every

It returns true if all elements pass the condition.

[Demo:](https://codepen.io/crsanti/pen/pwwvdj)

```javascript
const bookings = [
  {id:23453, price: 250, room: 'standard', prepaid: false, succeeded: true},
  {id:56456, price: 150, room: 'superior', prepaid: false, succeeded: true},
  {id:43243, price: 550, room: 'standard', prepaid: true, succeeded: false},
  {id:23223, price: 550, room: 'standard', prepaid: true, succeeded: true},
  {id:89232, price: 650, room: 'superior', prepaid: true, succeeded: false},  
];

const allSucceeded = bookings.every(booking => booking.succeeded);

console.log(allSucceeded);
// false
```

# Some

It returns true if at-least one pass the condition.

[Demo:](https://codepen.io/crsanti/pen/GEEgYe)

```javascript
const bookings = [
  {id:23453, price: 250, room: 'standard', prepaid: false, succeeded: true},
  {id:56456, price: 150, room: 'superior', prepaid: false, succeeded: true},
  {id:43243, price: 550, room: 'standard', prepaid: true, succeeded: false},
  {id:23223, price: 550, room: 'standard', prepaid: true, succeeded: true},
  {id:89232, price: 650, room: 'superior', prepaid: true, succeeded: false},  
];

const hasAnySuperiorRoom = bookings.some(booking => booking.room === 'superior');

console.log(hasAnySuperiorRoom);
// true
```
