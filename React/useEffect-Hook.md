# useEffect Hook in React

## Basic Syntax

```jsx
useEffect(() => {
  alert("Hello, from useEffect!");
}, []);
```

## Usage

Why would you use it

You use it when you want to render something on the screen when the component is in a particular state

For example, the above mentioned hook will run when the app is loaded for the first time.

When will this hook run, any guesses?

```jsx
useEffect(() => {
  alert("Hello, from the count variable");
}, [count]);
```

This will run twice:

First when the website is loaded as the count is set to zero initially.

Then it will run as the value is being changed.

It can run as many times as the value is being changed:

```jsx
function App() {
  const [count, setCount] = useState(0);

  // Here it is!!!!!!!
  useEffect(() => {
    alert("Hello, from the count variable");
  }, [count]);
  // -------

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

## Common usages

1. This will act on every render

```jsx
useEffect(() => {
  alert("Hello, from the count variable");
});
```

2. trigger when something changes

```jsx
useEffect(() => {
    alert("Hello, from useEffect!");
  }, [variable which will change]);
```

## Cleanup Function

It is executed when a component is unmounted.

What does it mean to unmount?

It means to delete a component or in real life when you disconnect connection from a server, then this block is executed.

**Syntax:**

```jsx
useEffect(() => {
  alert("Hello, from the count variable");

  return () => {
    alert("The count variable was unmounted");
  };
}, [count]);
```
