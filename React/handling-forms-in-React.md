# Handling Forms in React

When working with forms in react, you will need to make functions and event handlers for everything

but you can use `react-hook-forms` to make your life easier

It provides you Simple form validation

So to get started, make a simple form

```jsx
<form action="">
  <input type="text" placeholder="username" />
  <br />
  <input type="password" placeholder="password" />
  <br />
  <input type="submit" />
</form>
```

Then to add functionality install react-hook-form

```
npm install react-hook-form
```

and them import it on top of the react file

```jsx
import { useForm } from "react-hook-form";
```

Then add this thing in your app inside the main app function(preferably) but not inside the return statement

```jsx
const {
  register,
  handleSubmit,
  watch,
  formState: { errors },
} = useForm();
```

Make an onSubmit function and invoke it in the onSubmit of the form in the handleSubmit

handleSubmit is already defined for you by the react-hook-forms

```jsx
const onSubmit = (data) => console.log(data);

return (
  <>
    <form onSubmit={handleSubmit(onSubmit)}>...</form>
  </>
);
```

then we need to register out input by invoking the register function and giving the input a name

```jsx
{...register("example")}
```

Do this for for both input

```jsx
<form action="">
  <input type="text" placeholder="username" {...register("username")} />
  <br />
  <input type="password" placeholder="password" {...register("password")} />
  <br />
  <input type="submit" />
</form>
```

Then to add some validations, like min and max length and required field etc. Do the following

min or max length:

In this example, I will be adding the minimum length of 3 to the password field and the maximum length of 8 to the username field

To do that, make an object in the same register function after the name of your input

where you can use minLength or maxLength and then make another object which have 2 key value pairs i.e. value and the message

value being what is the length you want to specify and message being what you want to display when the condition is not met

```jsx
<form onSubmit={handleSubmit(onSubmit)}>
  <input
    type="text"
    placeholder="username"
    {...register("username", {
      maxLength: { value: 8, message: "maximum length is 8" }, //here
    })}
  />
  <br />
  <input
    type="password"
    placeholder="password"
    {...register("password", {
      minLength: { value: 3, message: "minimum length is 3" }, //here
    })}
  />
  <br />
  <input type="submit" />
</form>
```

Then if you want to display the error on the screen

you can use the formState of error

to do that, add curly brackets after your input and then catch the error as `errors` with the name of the input and then specify a condition, that if the error is true than display the message from the object that you specified earlier

like this

```jsx
{
  errors.username && <div>{errors.username.message}</div>;
}
```

this would look like this in the entire form:

```jsx
<form onSubmit={handleSubmit(onSubmit)}>
  <input
    type="text"
    placeholder="username"
    {...register("username", {
      maxLength: { value: 8, message: "maximum length is 8" },
    })}
  />
  <br />
  {errors.username && <div>{errors.username.message}</div>} //here
  <input
    type="password"
    placeholder="password"
    {...register("password", {
      minLength: { value: 3, message: "minimum length is 3" },
    })}
  />
  <br />
  {errors.password && <div>{errors.password.message}</div>} //here
  <input type="submit" />
</form>
```

required field:

add this beside the object where the minLength is

```jsx
required: { value: true, message: "password is required" },
```

Now when you submit this, it will display the username and password as object in the console.

If you want to learn how to add the loading thing and configure the `isSubmitting` function, I have made that another note

[isSubmitting Function in react-hook-forms](https://github.com/sarimhasan/Today-I-Learned/blob/main/React/isSubmitting-Function-in-react-hook-forms.md)
