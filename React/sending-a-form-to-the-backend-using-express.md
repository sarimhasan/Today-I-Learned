# Sending the form to the backend

Now if you want to send the information that the user had submitted to the backend, you can use express, body-parser, fetch API and a little bit of cors

First install express, cors, and body-parser

```shell
npm install express cors body-parser
```

Then make a folder in your main directory as `backend` and then make a `server.js` file inside it

import all of the modules

```js
import express from "express";
import cors from "cors";
import bodyParser from "body-parser";
```

Then make a simple hello world app using the get and post routes and initialize it on port 3000

follow this: [How to build an express Server with body-parser](https://github.com/sarimhasan/Today-I-Learned/blob/main/Express/Basic-Express-App-with-body-parser.md)

also add cors as the middleware with body-parser

```js
app.use(cors());
app.use(bodyParser.json());
app.use(bodyParser.urlencoded({ extended: true }));
```

then in the post route, `console.log` the `req.body`

```js
app.post("/", (req, res) => {
  console.log(req.body);
});
```

and in the app.jsx file, add these modifications to the onSubmit function

```jsx
const onSubmit = async (data) => {
  await delay(2);
  let r = await fetch("http://localhost:3000/", {
    method: "POST",
    headers: { "Content-Type": "application/JSON" },
    body: JSON.stringify(data),
  });
  let res = await r.text();
  console.log(data);
};
```

basically this function delays for 2 seconds, then sends a POST request to `http://localhost:3000/` with JSON-formatted data, waits for the response, and logs the original form data to the console.

Now what you have to do is that,

run both of the servers, frontend and the backend

run the `server.js` file on port 3000 and `App.jsx` file can be run on any port

but run them on separate terminals

And you will see the username and password as object in both the console in the browser and in the terminal where you started the server file
