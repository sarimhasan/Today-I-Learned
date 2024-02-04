# Basic React, Components and Props

There is an app.jsx file which is your main page file like the index.html file.
You have to write everything in a function.

```jsx
function Card() {
  return (
    <div className="card">
      <h1>Card</h1>
      <p>You can write the card description here</p>
    </div>
  );
}
```

You can only pass one tag in the return.

## Components

React shines because there is something called components which let you create your app in pieces and merge them in one file i.e. app.jsx

You can create components files in the component folder under the src folder

Then first import them at the top of the file like this:

```jsx
import Card from "./components/Card.jsx";
```

Then you can link them in the main function:

```jsx
function App() {
  return (
    <>
      <Card /> // Like this
      <Card /> // And Yeah, you can use them more than once
    </>
  );
}
```

## Props

You can pass props from the main app.jsx file ad the will be accepted in the component file and will render it accordingly.

This will help if you want to use a component more than once and have different content in them everytime.

You can pass them in the app.jsx file like this:

```jsx
function App() {
  return (
    <>
      <Card title="Card 1" description="This is the description of card 1" />
      <Card title="Card 2" description="This is the description of card 2" />
    </>
  );
}
```

And you can receive them in the component file like this:

```jsx
function Card(props) {
  return (
    <div className="card">
      <h1>{props.title}</h1>
      <p>{props.description}</p>
    </div>
  );
}
```

By calling `props` as the argument in Main function. Though you can name it whatever you want, props is generally used.

Then you can use them as `props.anyThing`.
But remember, whatever you call should be first passed through the main jsx file which is calling this component
