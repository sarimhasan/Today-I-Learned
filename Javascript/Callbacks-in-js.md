# Callbacks in Javascript

You do know that Javascript has an asynchronous nature, which means when a job is taking some time, then Javascript will skip that and proceed to the next job in the script

For example, in this code:

```js
function hello() {
  setTimeout(() => {
    console.log("Hello");
  }, 2000);
}

function goodbye() {
  console.log("Goodbye");
}

hello();
goodbye();
```

What do you expect the output to be, you guessed it right.

```
Goodbye
Hello
```

Javascript does not wait for the hello function to print the Hello statement after 2 seconds, instead it prints goodbye first then lets hello print after 2 seconds

But what if you want to wait for the data to come from the database and then you want to continue with the script

Well, you can use callbacks

A callback function is a function that is passed as an argument to another function

For example, you can say that after the hello function has executed then render the goodbye function or continue with the rest of the script

To do that, you can pass the goodbye function as the argument in the hello function without the parenthesis so that it does not execute immediately

and in the hello function take callback or any other name you want as the parameter and then invoke it at the end of the function

```js
function hello(callback) {
  setTimeout(() => {
    console.log("Hello");

    callback();
  }, 2000);
}

function goodbye() {
  console.log("Goodbye");
}
```

and invoke the hello function like this

```js
hello(goodbye);
```

The output will include hello after 2 seconds, followed by goodbye

```
Hello
Goodbye
```
