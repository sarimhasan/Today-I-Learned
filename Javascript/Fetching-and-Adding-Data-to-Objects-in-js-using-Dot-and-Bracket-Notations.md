# Dot and Bracket notation for Objects in javascript

# Fetching

We can fetch data from an object in JavaScript in 2 ways. For this example I am going to use this objects:

```js
const sarim = {
  firstName: "Sarim",
  lastName: "Hasan",
  age: 16,
  job: "Student",
  friends: ["Ayan", "Hussain", "Azbak"],
};
```

## Dot Notation

We use a dot after the name of the object and then write the name of the value that we need to fetch

```js
console.log(sarim.lastName);
```

This will output: `'Hasan'`.

## Bracket Notation

We can use square brackets after the name of the object like we used to do in [[Array Operations|arrays]] and put the name of the filed in the brackets or we can **put entire expressions as well**:

```js
// Simple example
console.log(sarim.["lastName"]) // Output: 'Hasan'

// Example with an expression
const nameKey = "Name";
console.log(sarim["first" + nameKey]) // It will concatonate the string and output the firstName.
```

# Adding

## Dot Notation

```js
sarim.location = "Pakistan";
```

## Bracket Notation

```js
sarim["city"] = "Karachi";
```
