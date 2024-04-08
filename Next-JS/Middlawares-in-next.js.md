# Middlewares in Express JS

To understand what middlewares are, see the note on [Middlewares in express](https://github.com/sarimhasan/Today-I-Learned/blob/main/Express/Middlewares-in-express.md)

for more info: visit [next.js](https://nextjs.org/docs/app/building-your-application/routing/middleware)'s website

basic syntax:

```js
import { NextResponse } from 'next/server';

// This function can be marked `async` if using `await` inside
export function middleware(request) {
  return NextResponse.redirect(new URL('/home', request.url));
}

// See "Matching Paths" below to learn more
export const config = {
  matcher: '/about/:path*',
};
```

It will redirect any traffic coming to the about page to the home page

what if you have changed your URL, for example, you have changed your about page from `https://example.com/about` to `https://example.com/about-2`

You can actually redirect the user or you can rewrite the the page here

difference between redirect and rewrite

|               Redirect                |                  Rewritre                  |
| :-----------------------------------: | :----------------------------------------: |
| It redirects the user to another page | It renders another page on the current URL |

if you want rewrite, you can use this syntax

```js
import { NextResponse } from 'next/server';

export function middleware(request) {
  if (request.nextUrl.pathname.startsWith('/about')) {
    return NextResponse.rewrite(new URL('/about-2', request.url));
  }
}
```
