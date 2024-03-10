# Dynamic Routing in Next.js

Dynamic Routering is provided by default by Next.js

So for example, you have many blogposts about different programming languages, and you want the user to add the name of the languages in the URL and land on the designated blogpost

you can do that by making a blogposts folder and a folder with this name: `[slug]`

and add your `page.js` file inside

Now you can paste this code in your `page.js` file

```js
export default function Page({ params }) {
  const languages = ["python", "javascript"];

  if (languages.includes(params.slug)) {
    return <div>Post of {params.slug}</div>;
  } else {
    return <div>No Post Found</div>;
  }
}
```

when a user accesses a URL like `localhost:3000/blogposts/python`

the result will be Post of python

but when a user tries to access a blogpost on java, which is not a language in the language string

the page will return: No Post found

## What is Slug

if you `console.log` the slug variable, it shows the value in a string you enter after the blogposts slash

which means if you enter `/blogpost/sarim`, the value of slug will be `sarim`
