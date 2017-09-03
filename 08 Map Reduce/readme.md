# Map

Iterates its elements in insertion order to apply a function and returns new array.

[Demo:](https://codepen.io/crsanti/pen/OggPZY)

```javascript
const bookings = [
  {id:23453, price: 250, room: 'standard', prepaid: false, succeeded: true},
  {id:56456, price: 150, room: 'superior', prepaid: false, succeeded: true},
  {id:43243, price: 550, room: 'standard', prepaid: true, succeeded: false},
  {id:23223, price: 550, room: 'standard', prepaid: true, succeeded: true},
  {id:89232, price: 650, room: 'superior', prepaid: true, succeeded: false},  
];

const discount = 10;
const discountedBookings = bookings.map(booking => ({
  ...booking,
  price: booking.price * (1 - (discount / 100))
}));

console.log(discountedBookings);
/*
  ​[
    Object {
      id: 23453,
      prepaid: false,
      price: 225,
      room: "standard",
      succeeded: true
    },
    Object {
      id: 56456,
      prepaid: false,
      price: 135,
      room: "superior",
      succeeded: true
    },
    Object {
      id: 43243,
      prepaid: true,
      price: 495,
      room: "standard",
      succeeded: false
    },
    Object {
      id: 23223,
      prepaid: true,
      price: 495,
      room: "standard",
      succeeded: true
    },
    Object {
      id: 89232,
      prepaid: true,
      price: 585,
      room: "superior",
      succeeded: false
    }
  ]
*/
```

# Reduce

Iterates its elements from left to right to apply a function to reduce it to a single value.

[Demo:](https://codepen.io/crsanti/pen/XggJPg)

```javascript
const bookings = [
  {id:23453, price: 250, room: 'standard', prepaid: false, succeeded: true},
  {id:56456, price: 150, room: 'superior', prepaid: false, succeeded: true},
  {id:43243, price: 550, room: 'standard', prepaid: true, succeeded: false},
  {id:23223, price: 550, room: 'standard', prepaid: true, succeeded: true},
  {id:89232, price: 650, room: 'superior', prepaid: true, succeeded: false},  
];

const totalPrice = bookings.reduce((total, booking) => total + booking.price, 0);

console.log(totalPrice);
// 2150
```

[Reduce right.](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/ReduceRight)
