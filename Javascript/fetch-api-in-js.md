# Fetch API in Javascript

Fetch API can be used for making HTTP requests to fetch resources like images, files, JSON style data etc.

format/syntax: `fetch(url, {options})`

The fetch function is a [Promises](https://github.com/sarimhasan/Today-I-Learned/blob/main/Javascript/Promises-in-js.md) based, which means it will either be rejected or resolved by the server

In this demo I am using a Pokémon API to get data

To start, first make an [asynchronous](https://github.com/sarimhasan/Today-I-Learned/blob/main/Javascript/Async-and-await-in-js.md) function and make a try and catch block inside it

```js
async function fetchData() {
  try {
  } catch (error) {}
}
```

Then assign a const variable the fetch function after the await keyword as `fetch()` returns a promise

and place your API endpoint inside the fetch function as string

then make an `if/else` statement to throw an error when a user enters a Pokémon which is not defined in the API

and in the catch block `console.log` the error

```js
async function fetchData() {
  try {
    const response = await fetch(
      "https://pokeapi.co/api/v2/pokemon/typhlosion"
    );

    if (!response.ok) {
      throw new Error(
        "You son of bitch is trying to fetch some data that is not there"
      );
    }
  } catch (error) {}
}
```

Then to convert the response to JSON data use the `json()` function

And this function is also promise based, which means you need to use the await keyword again for it to first get the data and then continue with the script

and then finally console log the data

```js
async function fetchData() {
  try {
    const response = await fetch(
      "https://pokeapi.co/api/v2/pokemon/typhlosion"
    );

    if (!response.ok) {
      throw new Error(
        "You son of bitch is trying to fetch some data that is not there"
      );
    }

    const data = await response.json();
    console.log(data);
  } catch (error) {}
}
```

Then you would get an object and can further filter it using the bracket [notation](https://github.com/sarimhasan/Today-I-Learned/blob/main/Javascript/Fetching-and-Adding-Data-to-Objects-in-js-using-Dot-and-Bracket-Notations).
