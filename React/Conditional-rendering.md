# Conditional Rendering

You use conditional rendering when you want to display or hide some components under some conditions.

For example, you might want to show some text when a user clicks on it and then you want to hide it when the user clicks on it the second time.

Here is the code for that:

```jsx
function App() {
  const [showBtn, setshowBtn] = useState(true);

  function handleClick() {
    setshowBtn(!showBtn);
  }

  return (
    <>
      <button onClick={handleClick}>
        {showBtn ? "Hide Text" : "Display Text"}
      </button>
      <p>
        {showBtn
          ? "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Pariatur neque quibusdam, quas expedita natus, harum totam quo beatae exercitationem aliquid fuga?"
          : null}
      </p>
    </>
  );
}
```

This not only hides and show the text, but also changes the text of the button accordingly too

> [!NOTE]
> When you want to show different outputs on every situation then use the above syntax.
>
> But if you want to show only one thing than you can use the logic `&&` operator

## Logic && (AND)

If we want to make it more shorter, we can use the logic operator `&&`

Which in itself is an AND Gate.

```jsx
function App() {
  const [showBtn, setshowBtn] = useState(true);

  function handleClick() {
    setshowBtn(!showBtn);
  }

  return (
    <>
      <button onClick={handleClick}>
        {showBtn ? "Hide Text" : "Display Text"}
      </button>

      {showBtn && (
        <p>
          Lorem, ipsum dolor sit amet consectetur adipisicing elit. Pariatur
          neque quibusdam, quas expedita natus, harum totam quo beatae
          exercitationem aliquid fuga?
        </p>
      )}
    </>
  );
}
```

It translates as

If the showBtn variable is true than display the text otherwise display nothing.

AND Gate means to multiply which means, both the values need to be one in order to be able to output something.

When only one thing is false then the output becomes zero.
