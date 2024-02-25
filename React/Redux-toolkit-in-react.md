# How to use redux toolkit

OK, so react Redux Toolkit helps you access any state in any of the component

So to start, install Redux

```shell
npm install @reduxjs/toolkit react-redux
```

Then make a folder in your `src` directory as `redux` and make a file called `store.js`

The store basically stores the applications state data

Add this code in the store file

```js
import { configureStore } from "@reduxjs/toolkit";

export const store = configureStore({
  reducer: {},
});
```

Then we can make it available to our React components by putting a React-Redux `<Provider>` around our application in `src/main.jsx`. Import the Redux store we just created, put a `<Provider>` around your `<App>`, and pass the store as a prop

```jsx
import React from "react";
import ReactDOM from "react-dom";
import "./index.css";
import App from "./App";
import { store } from "./redux/store.js"; //here
import { Provider } from "react-redux"; //here

ReactDOM.render(
  <Provider store={store}>
    {" "}
    //here
    <App />
  </Provider>, //here
  document.getElementById("root")
);
```

Then make a folder in your redux folder for the thing you want to do like `cart`, if in an e-commerce website. But for this example, I will make a `counter` folder and make a `counterSplice.js` file in it

Then import the createSplice API in that file

along with all of this boiler plate code

```js
import { createSlice } from "@reduxjs/toolkit";

const initialState = {
  value: 0,
};

export const counterSlice = createSlice({
  name: "counter",
  initialState,
  reducers: {
    increment: (state) => {
      // Redux Toolkit allows us to write "mutating" logic in reducers. It
      // doesn't actually mutate the state because it uses the Immer library,
      // which detects changes to a "draft state" and produces a brand new
      // immutable state based off those changes
      state.value += 1;
    },
    decrement: (state) => {
      state.value -= 1;
    },
    incrementByAmount: (state, action) => {
      state.value += action.payload;
    },
  },
});

// Action creators are generated for each case reducer function
export const { increment, decrement, incrementByAmount } = counterSlice.actions;

export default counterSlice.reducer;
```

So what is this doing is first, setting the state of the variable = 0

Then creating a function, in which it defines the name along with importing the initial state and making a `reducers` key value pair

so what is a reducer

A reducer is a function that returns some state data. Is triggered by an action

you can make some functions inside it for the things you want to do with the state

In this example, increment and decrement

Action is what tells reducer  to manipulate the store data, it carries the name and (not required) some data.

And lastly it exports the actions and the reducer(by default)

Then import the reducer function from from counter slice and add it to our store

```js
import { configureStore } from "@reduxjs/toolkit";
import counterReducer from "../features/counter/counterSlice"; //here

export const store = configureStore({
  reducer: {
    counter: counterReducer, //this
  },
});
```

Now you can import the `useSelector` and `useDispatch` hooks from react redux alongside the increment and decrement functions from your `counterSlice.js` file

```jsx
import { useSelector, useDispatch } from "react-redux";
import { decrement, increment } from "./counterSlice";
```

then you can make a variable as counter and catch your state

and also initialize the dispatch function

```jsx
const count = useSelector((state) => state.counter.value);
const dispatch = useDispatch();
```

You only need the count variable where ever you want to just read your variable

and when you want to write that variable, you need that dispatch function

For example, you can call this in any of your component file and excess the state and change it

now how can you use that dispatch function?

Pass it through an arrow function in the event of an object

```jsx
return (
  <>
    <div className="">The value of count is: {count}</div>
    <button onClick={() => dispatch(decrement())}>Subtract</button>//this
    <button onClick={() => dispatch(increment())}>Add</button>//this
  </>
);
```
