# Custom 404 Page in Next.js

When you access a resource which is not present on your server

then the server gives a 404 page

You can easily customize the 404 page in next.js by creating a file in the app directory as `not-found.js`

and put anything you would like in that function

```jsx
import Link from "next/link";

export default function NotFound() {
  return (
    <div>
      <h2>Not Found</h2>
      <p>You are trying to access a resource which is not there</p>
      <Link href="/">Return Home</Link>
    </div>
  );
}
```

This is a basic 404 page, but you can customize it as you wish just like customizing a web page using react
