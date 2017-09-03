# Class

Class is a well known concept on other OOP languages as C#, Java... What a class
basically brings in all this languages is state and behavior for a given domain 
concept. For example a car needs tires and start its engine. Although this concept
is new in ES6, it's an old mate that has been a round for a while. Because class, 
is just a syntactic sugar for the prototype pattern. 


# Steps

Let's create a 'class' using the prototype pattern.

```javascript
var Car = function () {
  this.speed = 0;
  this.started = false;
};

Car.prototype.startEngine = function () {
  this.started = true;
};

Car.prototype.offEngine = function () {
  this.started = false;
  this.speed = 0;
};

Car.prototype.speedUp = function (amount) {
  if (this.started) {
    this.speed += amount;
  }
};

Car.prototype.getSpeed = function () {
  return this.speed;
};

var car = new Car();
car.startEngine();
car.speedUp(3);
console.log(car.getSpeed());
car.offEngine();
console.log(car.getSpeed());

```

Let's build the same using class:

```javascript
class Car {
  constructor() {
      this.speed = 0;
      this.started = false;
  }
  
  startEngine() {
      this.started = true;
  }
  
  offEngine() {
    this.started = false;
    this.speed = 0;
  }
  
  speedUp(amount) {
    this.speed += amount;
  }
  
  getSpeed() {
    return this.speed;
  }
}

var car = new Car();
car.startEngine();
car.speedUp(3);
console.log(car.getSpeed());
car.offEngine();
console.log(car.getSpeed());

```

As we can see classes bring us some advantages such the constructor and
methods are not separate, and we have to typ less to achieve the same result.
