# Hooks and States in React

## What is a State

State is basically just the component's memory. We use states when we want to change the what's on screen after an interaction. And **state is what remembers that interaction**.

## Why use state instead of local variables

When you change the variable in the code, react doesn’t realize it needs to render the component again with the new data.

Then you would need to render the React DOM again again just to see that variable.

This is where you use hooks and states

# What is a Hook?

_Hooks_ are special functions that are only available while React is rendering They **let you “hook into” different React features**.

## Let's build a counter

### Without hooks

```jsx
function App() {
  let count = 0;

  function plus1() {
    count = count + 1;
  }

  return (
    <>
      <div>
        <h1>The count is {count}</h1>
        <button onClick={plus1}>Update Count</button>
      </div>
    </>
  );
}
```

This does not work. **Why?**

It does increase the count of var count as you press the button.
But the problem is, that it **does not render that to the screen**.

### With Hooks

```jsx
function App() {
  const [count, setCount] = useState(0);

  function plus1() {
    setCount(count + 1);
  }

  return (
    <>
      <div>
        <h1>The count is {count}</h1>
        <button onClick={plus1}>Update Count</button>
      </div>
    </>
  );
}
```
