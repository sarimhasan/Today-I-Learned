# Server Actions in Next.js

This is a new feature in next js which lets you handle form submissions and data mutations

to get started, make an `actions/form.js`

server action asynchronous functions are a part of [[Next JS Server side vs Client Side|server side]] components

So to use them you need to specify `"use server"` at the top of your `form.js` file

then in your `page.js` file or where you decide to make your form component, add `"use client"` at the top because we are going to use some client components

make a form component and set its action as a function in the `form.js` file, and yes you will also need to import it, but we will do it later when we make the function in the file

```jsx
<form action={submitAction}>
  <p>Name</p>
  <input type="text" name="name" id="name" className="border-2" />
  <p>Location</p>
  <input type="text" name="location" id="location" className="border-2" />
  <br />
  <button className="border-2 my-2 py-1 px-2" type="submit">
    Submit
  </button>
</form>
```

I have assigned some tailwind classes to make it look a little bit better

Now let's build the `submitAction` function in the `form.js` file

lets say, when the the user submits the form, you want to make a file with the user's name and their location

to make a file you would need to use the `fs` module, so import it

then make a `writeFile()` function with await to make the file with the name of user and the extension as `.txt`

Then write the info as `Username is xxxx and they live in yyyyy`

you can also add a `console.log` so that you can see the values entered in the console too

And yeah you would also need to export the function

```js
"use server";
import fs from "fs/promises";

export async function submitAction(e) {
  console.log(e.get("name"), e.get("location"));
  await fs.writeFile(
    `clients/${e.get("name").toLowerCase()}.txt`,
    `The username is ${e.get("name")} and they live in ${e.get("location")}`
  );
}
```

To get the data, in next.js, we use the `.get()` method and inside the property name as string

Now also import this function in your form component file

```js
import { submitAction } from "@/actions/form";
```

Now when you run the form and submit some data, you will see a `client` directory in your root directory

and there will be a text file with the user's name and their location inside
