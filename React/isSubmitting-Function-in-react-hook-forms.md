# isSubmitting Function and simulating delay in React

How to set up the basic form handling: [[Handling Forms in React|here]]

add the isSubmitting function in the formState

```jsx
const {
  register,
  handleSubmit,
  watch,
  formState: { errors, isSubmitting }, //here
} = useForm();
```

Now you can access it in the return thing of your react app and make a condition that if `isSubmitting === true` then display a dive with some Loading... text in it

like this

```jsx
{
  isSubmitting && <div>Loading...</div>;
}
```

but you won't see that because everything happens instantly

to simulate some delay as you would face in real apps when you are sending the data to be verified or to store it in the database

to do that make a function called delay with a return promise and setTimeout function

```jsx
const delay = (d) => {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve();
    }, d * 1000);
  });
};
```

but you need to call it somewhere.

We are going to call it in the onSubmit function

start by making it an asynchronous function and you can call your delay function with how many seconds you want to delay as the argument

```jsx
const onSubmit = async (data) => {
  await delay(2);
  console.log(data);
};
```

Now when you submit your form, you will see the loading text on your screen for 2 seconds and after that your form will be submitted

and the text will disappear

finally how can you [[sending a form to the backend(Express) with react-hook-forms|send this form to the backend]]
