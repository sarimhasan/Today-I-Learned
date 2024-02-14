# What are Event Handlers

Definition from the react [website](https://react.dev/learn/responding-to-events):

> [!note]Definition
>
> Event handlers are your own functions that will be triggered in response to interactions like clicking, hovering, focusing form inputs, and so on.

For example:

This is a button that does nothing

```jsx
function App() {
  return (
    <>
      <div className="button">
        <button>Click me, Please!</button>
      </div>
    </>
  );
}
```

So to add some interaction, for example, display an alert when you click the button, you can add an event handler

```jsx
function App() {
  function handleClick() {
    alert("I was click!");
  }

  return (
    <>
      <div className="button">
        <button onClick={handleClick}>Click me, Please!</button>
      </div>
    </>
  );
}
```

Now it will display an alert whenever the button is clicked.

There are many more event handlers like onMouseClick etc. but you will learn them as you move forward
