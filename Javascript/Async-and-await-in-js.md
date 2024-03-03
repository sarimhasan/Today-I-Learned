# Async and Await in Javascript

What is async/await

in theory async makes a function return a promise

and await make an async function wait for a promise

So using the previous example of chores from [Promises in Javascript](https://github.com/sarimhasan/Today-I-Learned/blob/main/Javascript/Promises-in-js.md)

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

How would you display them in-order in the console or on the screen or whatever you would want to do with the data in real life

make an async function and make a variable which will receive the value of the chores' function

and console log the variable to see the value of the function

```js
async function doChores() {
  const walkDogResult = await walkDog();
  console.log(walkDogResult);

  const cleanKitchenResult = await cleanKitchen();
  console.log(cleanKitchenResult);

  const takeTrashResult = await takeTrash();
  console.log(takeTrashResult);

  console.log("You completed all the chores");
}
```
