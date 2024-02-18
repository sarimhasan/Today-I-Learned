# React Routering

## Installing

React Router is a npm package that you can install, which lets you navigate pages without refreshing the page

The question you might ask, what is wrong in refreshing pages? The answer I quit don't know myself.

But it has something to do with browser history and somethings as well

So, to start, install the package by running this command:

```
npm i react-router-dom
```

## Basic routering

Make some pages and a navbar.

But instead of using anchor tag to specify the link, use `<Link>...</Link>`.

But first yeah you need to import it in the component file:

```jsx
import { Link } from "react-router-dom";
```

The Navbar could look like this:

```jsx
const Navbar = () => {
  return (
    <div>
      <nav>
        <Link to="/">
          <li>Home</li>
        </Link>
        <Link to="/about">
          <li>About</li>
        </Link>
        <Link to="/contact">
          <li>Contact us</li>
        </Link>
      </nav>
    </div>
  );
};
```

And yes, you need to specify the address as the `to=""` tag. And they will be converted to href and anchor tags while rendering

Now how would you do the routering?

Ans. In the app/main file.

First, import `createBrowserRouter` and `routerProvider`:

```jsx
import { createBrowserRouter, RouterProvider } from "react-router-dom";
```

**As well as import all your pages/components**

Then make a function which describes all your routes

```jsx
const router = createBrowserRouter([
  {
    path: "/",
    element: (
      <>
        <Navbar /> <Home />
      </>
    ),
  },
  {
    path: "/about",
    element: (
      <>
        <Navbar /> <About />
      </>
    ),
  },
  {
    path: "/contact",
    element: (
      <>
        <Navbar /> <Contact />
      </>
    ),
  },
]);
```

Inside the function, make an array and then inside that make some objects.

Inside which make two properties, `path` and `element`

for path define the path in a string and for element, add the component in some react closings

Then at the return paste this with your router variable as the parameter:

```jsx
<RouterProvider router={router} />
```

## Dynamically changing styles of the `li` element

To change the color of the li element that you are currently on.

You can do this

First change all the `<Link>...</Link>` to `<NavLink>...</NavLink>`

And yes, again, you need to import that first.

Remove this line from before

```jsx
import { Link } from "react-router-dom";
```

And add this line:

```jsx
import { NavLink } from "react-router-dom";
```

Then when you are on a page and one of the li element is active, it will automatically give you an `active` class

Which you can then target in your CSS file to change the background color or any other style

```css
.active {
  color: red;
}
```
