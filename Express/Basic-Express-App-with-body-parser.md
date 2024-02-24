# Basic Express App with Body Parser

### Steps

1. First `cd` into the new directory.
2. make the `index.js` using the `touch` command in the terminal or using the file browser
3. run `npm init`
4. put this starter code:

```js
import express from "express";
const app = express();
const port = 3000;

app.get("/", (req, res) => {
  res.send("Hello World!");
});

app.listen(port, () => {
  console.log(`The app is running on port ${port}`);
});
```

6. run the server using nodemon: `nodemon index.js`
7. Now if you want to abb body parser as your [[Middlewares in express|middleware]] that first install it using `npm i body-parser`
8. and here is the code for using it:

```js
import express from "express";
import bodyParser from "body-parser";
import { dirname } from "path";
import { fileURLToPath } from "url";
const __dirname = dirname(fileURLToPath(import.meta.url));

const app = express();
const port = 3000;

app.use(express.static("public"));
app.use(bodyParser.urlencoded({ extended: true }));

app.get("/", (req, res) => {
  res.sendFile(__dirname + "/public/index.html");
});

// This is only for post route
app.post("/url", (req, res) => {
  res.send("You put here what you want");
});

app.listen(port, () => {
  console.log(`Listening on port ${port}`);
});
```
