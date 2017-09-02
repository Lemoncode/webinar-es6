# Filter

It returns a new array with all elements that pass condition.

[Demo bookings failed](https://codepen.io/crsanti/pen/VWWYrx)

```javascript
const bookings = [
  {id:23453, price: 250, room: 'standard', prepaid: false, succeeded: true},
  {id:56456, price: 150, room: 'superior', prepaid: false, succeeded: true},
  {id:43243, price: 550, room: 'standard', prepaid: true, succeeded: false},
  {id:23223, price: 550, room: 'standard', prepaid: true, succeeded: true},
  {id:89232, price: 650, room: 'superior', prepaid: true, succeeded: false},  
];

const unsucceededBookings = bookings.filter(booking => !booking.succeeded);

console.log(unsucceededBookings);
/*
  [
    Object {
      id: 43243,
      prepaid: true,
      price: 550,
      room: "standard",
      succeeded: false
    },
    Object {
      id: 89232,
      prepaid: true,
      price: 650,
      room: "superior",
      succeeded: false
    }
  ]
*/
```

```javascript
const bookingsVip = bookings.filter(booking => booking.price > 500);

console.log(bookingsVip);
/*
  [
    Object {
      id: 43243,
      prepaid: true,
      price: 550,
      room: "standard",
      succeeded: false
    },
    Object {
      id: 23223,
      prepaid: true,
      price: 550,
      room: "standard",
      succeeded: true
    },
    Object {
      id: 89232,
      prepaid: true,
      price: 650,
      room: "superior",
      succeeded: false
    }
  ]
*/
```

# Find

It returns first element that pass condition.

[Demo pass condition](https://codepen.io/crsanti/pen/LLLEQQ)

```javascript
const bookings = [
  {id:23453, price: 250, room: 'standard', prepaid: false, succeeded: true},
  {id:56456, price: 150, room: 'superior', prepaid: false, succeeded: true},
  {id:43243, price: 550, room: 'standard', prepaid: true, succeeded: false},
  {id:23223, price: 550, room: 'standard', prepaid: true, succeeded: true},
  {id:89232, price: 650, room: 'superior', prepaid: true, succeeded: false},  
];

const booking = bookings.find(booking => booking.room === 'standard');

console.log(booking.id);
// 23453
```

[Demo fail condition](https://codepen.io/crsanti/pen/qjjzjB)

```javascript
const booking = bookings.find(booking => booking.room === 'suite');

console.log(booking);
// undefined
```

# FindIndex

Similar to `.find` but it returns index instead of element.

[Demo pass condition](https://codepen.io/crsanti/pen/RggNMe)

```javascript
const bookings = [
  {id:23453, price: 250, room: 'standard', prepaid: false, succeeded: true},
  {id:56456, price: 150, room: 'superior', prepaid: false, succeeded: true},
  {id:43243, price: 550, room: 'standard', prepaid: true, succeeded: false},
  {id:23223, price: 550, room: 'standard', prepaid: true, succeeded: true},
  {id:89232, price: 650, room: 'superior', prepaid: true, succeeded: false},  
];

const index = bookings.findIndex(booking => booking.room === 'standard');

console.log(index);
// 0

console.log(bookings[index].id);
// 23453
```

[Demo fail condition](https://codepen.io/crsanti/pen/yXXrXL)

```javascript
const index = bookings.findIndex(booking => booking.room === 'suite');

console.log(index);
// -1
```
