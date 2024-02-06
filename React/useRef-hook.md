# useRef Hook in React

useRef hook lets you preserve values between renders.

So what does that mean?

It means when for example, I click a counter, the component is re-rendered. But what if you want to know how many times you have clicked on it. You can't because every time it is newly rendered and the count is lost.

(Not the count of the useState but the count of a variable)

Counter without useRef:

```jsx
function App() {
  const [count, setCount] = useState(0);

  let a = 0;

  function handleClick() {
    setCount(count + 1);
  }

  useEffect(() => {
    console.log((a = a + 1));
  });

  return (
    <>
      <div>
        <h1>The count is {count}</h1>
        <button onClick={handleClick}>Update the count</button>
      </div>
    </>
  );
}
```

The count of variable is a is lost everytime and it goes to `1`.

But you can use useRef hook to remember the count as it persists data between renders.

**Syntax:**

```jsx
const n = useRef(initialValue);
```

This outputs an object named as `current`

So you can reference it by calling `variableName.current`

Counter with useRef:

```jsx
function App() {
  const [count, setCount] = useState(0);
  const a = useRef(0);
  // let a = 0;

  function handleClick() {
    setCount(count + 1);
  }

  useEffect(() => {
    console.log((a.current = a.current + 1));
  });

  return (
    <>
      <div>
        <h1>The count is {count}</h1>
        <button onClick={handleClick}>Update the count</button>
      </div>
    </>
  );
}
```

So this time it persists the value and outputs the correct number sequence.

## Using ref in DOM

We can reference elements using the useRef hook to change their properties.

For example:

```jsx
function App() {
  const btnRef = useRef();

  function handleClick() {
    btnRef.current.style.backgroundColor = "pink";
  }

  return (
    <>
      <div>
        <button ref={btnRef} onClick={handleClick}>
          Change my color
        </button>
      </div>
    </>
  );
}
```

So now when we click on the button its color is going to change to pink

1. Leave the useRef function calling empty
2. Define the ref in the element as the useRef variable
