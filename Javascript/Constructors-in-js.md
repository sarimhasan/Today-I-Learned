# Constructors in Javascript

More modern and cleaner way to make objects dynamically would be to use [[Classes in Javascript]]

We use JS constructers to create objects easily

For example, if you want to create data as objects of all the cars in your showroom, then you would have to manually create hundreds of objects

But with constructers, you can easily do that

first make a function and remember to make the name start with a capital letter and then pass all the options as parameters.

Define all the properties using the `this` keyword and then assign them the appropriate parameters

```js
function Car(make, model, year, color) {
  this.make = make;
  this.model = model;
  this.year = year;
  this.color = color;
}
```

Then define the new car object using a variable and pass the information as arguments

```js
const car1 = new Car("Toyota", "Fortuner Legender", 2024, "white");
```

Then you can access them in the console or whatever you want to do with them

```js
console.log("Car 1");
console.log(car1.make);
console.log(car1.model);
console.log(car1.year);
console.log(car1.color);
```

Your response:

```
Car1
Totota
Fortuner Legender
white
```

You can create how many objects you want and also can rename the parameters you want, but make them easy to understand
