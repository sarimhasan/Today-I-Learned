# Promises in Javascript

When you use too many callbacks, you enter something called as a callback hell

where the code is very hard to read

but in modern javascript, you use promises.

Promise is an object that manages asynchronous operations

and it "promises to return a value"

so how you would use it

For example, you have 3 chores to do

1. Walk the dog
2. Clean the kitchen
3. Take the trash out

and you are supposed to do them in order and all of them takes different amount of time,

first you would make a function and add the `console.log` in the Promise method by first defining it using the `new` keyword then inside an arrow or an anonymous function which will give you 2 parameters, `resolve` and `reject` and inside you can put a `setTimeout` function to simulate delay

then use the resolve parameter to write what you want to display if the promise is resolved

```js
function walkDog() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve("You walked the dog");
    }, 2000);
  });
}

function cleanKitchen() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve("You cleaned the kitchen");
    }, 1500);
  });
}

function takeTrash() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve("You took the trash out");
    }, 1000);
  });
}
```

Then if you want to see them in action inside the console, you can use method chaining

and also use the `.then` method to console log the value promise gave you

```js
walkDog()
  .then((value) => {
    console.log(value);
    return cleanKitchen();
  })
  .then((value) => {
    console.log(value);
    return takeTrash();
  })
  .then((value) => {
    console.log(value);
    console.log("You finished all the chores");
  });
```

Now if you want to use a more proper way of showing it to the console or do anything with your data, use [[Async and Await in Javascript]]
