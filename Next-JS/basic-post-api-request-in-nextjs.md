# Basic POST API Request in Next.js

Next.js is a full-stack framework for React which means it also offers backend functionality alongside frontend

So lets build an API to POST a request to the server to post submit some data

If you had this data

```js
const data = {
  name: "Sarim Hasan",
  job: "Student",
  age: 16,
};
```

paste this data in the same file as your `handleClick` function

how can you POST it to the server

First make a folder called API in the app folder and then an add folder inside it and a `route.js` file inside it

Then just to make a POST request paste this code:

```js
import { NextResponse } from "next/server";

export async function POST(request) {}
```

and then inside the `page.js`, you can make a button so that when you press it, it makes the request

```jsx
<button onClick={handleClick}>Click Me</button>
```

Then you can make an asynchronous function to make the POST request using the fetch API to the `api/add` folder where the `route.js` file is

Then catch the data by making another variable and awaiting the response and jsonify it

finally, console logging the data

```js
async function handleClick() {
  const response = await fetch("/api/add", {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
    },
    body: JSON.stringify(data),
  });

  const data = await response.json();
  console.log(data);
}
```

Then in the `route.js` file, you need to receive the requested data and deliver a message to the user

```js
export async function POST(request) {
  const data = await request.json();
  console.log(data);
  return NextResponse.json({
    success: true,
    data: "Your request was Successful",
  });
}
```

Now when you press the button, you will get a message: `Your request was successfull` in the browser's console.
