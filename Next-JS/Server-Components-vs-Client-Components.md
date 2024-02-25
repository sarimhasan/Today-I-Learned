# Server Side vs Client Side

So Next JS is a full stack framework, which means it handles both the backend and the frontend

So if you `console.log` a string in a normal file of react, it will not show in the browser console

because next js by default renders a page in the backend server and then parse the html to the browser

So first let's clear what is the client side and what is server side

Server side is the backend, in other words in your IDE console.

But client side is what the user renders on their computers, i.e. in the browser.

So if you want to use client components, you can add a simple line of code on top of your `js` file

```js
"use client";
```

## When to use what

When you want to access client side components like `useState` or any other hook, or use any browser API etc.

Then you might want to use **client components**

But when you might want to use tools like SEO, security, Data Fetching etc.

Then you will use server side rendering or **server components**

For more information, visit the next js website:

- [Client Side Components](https://nextjs.org/docs/app/building-your-application/rendering/client-components)
- [Server Side Components](https://nextjs.org/docs/app/building-your-application/rendering/server-components)
