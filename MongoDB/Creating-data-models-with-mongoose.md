# Data Modelling with Mongoose

For data modelling you obviously need to first install mongoose

After that make a file in models folder preferably named as `.models.js`. For example, `users.models.js`

then you need some boiler plate code

first import mongoose and then make a constant variable to make a new mongoose schema and then make an object inside

At the end, make a new variable to export the schema as mongoose model

the schema function also provides you with timestamps which gives you 2 properties to identify when the document was created and modified last. You can see the [documentation](https://mongoosejs.com/docs/timestamps.html)

```js
import mongoose from 'mongoos';

const userSchema = new mongoose.Schema({}, { timestamps: true }); //timestamps

export const User = mongoose.model('User', userSchema);
```

Now you can define all your properties and their types in the first object in the schema function

Mongoose also gives you more parameters like `required` and `lowercase`, which really helps.

So you can create some fields like this:

```js
import mongoose from 'mongoos';

const userSchema = new mongoose.Schema(
  {
    username: {
      type: String,
      required: true,
      unique: true,
      lowercase: true,
    },
    email: {
      type: String,
      required: true,
      unique: true,
      lowercase: true,
    },
    password: {
      type: String,
      required: true,
      lowercase: true,
    },
  },
  { timestamps: true }
);

export const User = mongoose.model('User', userSchema);
```
