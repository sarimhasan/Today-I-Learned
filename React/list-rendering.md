# Rendering Lists in React

If you want to render a list in react. Follow along

First make an array of data outside of your main App function:

```jsx
const items = ["apple", "banana", "mango", "orange"];
```

While using arrays in react, it gives you 2 built in methods. `map()` and `filter()`.

You can use map to map out the entire array at once by passing an arrow function inside it, like this:

```jsx
function App() {
  const listItems = items.map((fruit) => <li>{fruit}</li>);
  return <ul>{listItems}</ul>;
}

export default App;
}
```

This will render out the entire array as an ordered list

Now you will be having an an error saying that you need to define a key prop.

So to do that we need to have an id in every object so that react can distinguish between them.

We will use this array now:

```jsx
const items = [
  {
    id: 1,
    name: "apple",
    calories: 95,
  },
  {
    id: 2,
    name: "banana",
    calories: 105,
  },
  {
    id: 3,
    name: "mango",
    calories: 70,
  },
  {
    id: 4,
    name: "orange",
    calories: 45,
  },
];
```

Now you can define a key while returning the array

```jsx
function App() {
  const listItems = items.map((fruit) => (
    <li key={fruit.id}>
      {" "}
      // Like I have done here
      {fruit.name}: {fruit.calories}
    </li>
  ));
  return <ol>{listItems}</ol>;
}
```

So how do you **filter**

We use the `filter()` method

```jsx
function App() {
  const lowCalFruits = items.filter((fruit) => fruit.calories < 100); //Filter

  const listItems = lowCalFruits.map((fruit) => (
    <li key={fruit.id}>
      {fruit.name}: {fruit.calories}
    </li>
  ));
  return <ol>{listItems}</ol>;
}
```

So now the output will only show fruit with calories of 100 below i.e. apple, mango and orange.
