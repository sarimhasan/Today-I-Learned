# Dynamic Routering

When you want to have dynamic routering. You will need to add some parameters in the main app file in the router function's path property

For example:

```jsx
const router = createBrowserRouter([
  {
    path: "/user/:username",
    element: (
      <>
        <User />
      </>
    ),
  },
]);
```

See, the parameter after the path.

Now you need to catch the parameter in the `user` component file

by first obviously importing them:

```jsx
import { useParams } from "react-router-dom";
```

Then, you can define a variable to catch all the parameters from the main file:

```jsx
let params = useParams();
```

The you can do something like this:

```jsx
return (
  <div>
    <h1>Hello, I am {params.username}</h1>
  </div>
);
```

Now when you go to the URL and and something like this `http://localhost:5173/user/sarim`

Then you will see the username displayed dynamically on the webpage
