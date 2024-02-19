# useContext Hook in react

What if you want to pass some kind of information from a parent component to a children component.

Then you might use props.

But as your app grows, and you have a structure like this:

![](https://iili.io/JEi9cOP.png)

And you want for example, a use state counter from the main app file to use in the component

Then you will have to pass props from the main file then catch in the navbar then pass it again in the button file then again catch it in the button file then again pass it to the component and also catch it that file to use it.

This is called prop drilling:

![](https://iili.io/JEiHuIt.png)

But there is something called useContext which you can use

Which lets you access information to any distant children

![](https://iili.io/JEiHEpS.png)

To begin, make a folder in the src directory as context then make a `js` file, for example `context.js`.

then start with importing createContext from react

```js
import { createContext } from "react";
```

Then make a variable and set the value as createContext function and set an initial value:

```js
export const counterContext = createContext(0);
```

Then in the main parent file, import the context:

```js
import { counterContext } from "./context/context";
```

And then add a `.provider` tag to wrap all of the elements, with the value parameter as the variable that you want to pass

```jsx
<counterContext.Provider value={count}>...</counterContext.Provider>
```

Then where you want to access that count variable, you can start by first importing the useContext hook along with the context js file

```jsx
import { useContext } from "react";
import { counterContext } from "../context/context";
```

Then make a variable in the main component function but outside the return brackets.

Set the variable to catch the the counter variable by using the useContext hook and inside the variable name of the createContext file:

```jsx
const counter = useContext(counterContext);
```

Then you can use the variable any where such as:

```jsx
return (
  <>
    <div>{counter}</div>
  </>
);
```
