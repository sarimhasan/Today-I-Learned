# Connecting to MongoDB Atlas

```js
async function dbConnect() {
  try {
    const connectionInstance = await mongoose.connect(
      `${process.env.MONGODB_URI}/${DB_NAME}`
    );
    console.log(
      `\n MongoDB connected !! DB HOST: ${connectionInstance.connection.host}`
    );
  } catch (error) {
    console.log('Error: ', error);
    process.exit(1);
  }
}
```

This is the professional way to connect to the data base

yes, first import mongoose and your database name that I have in other files named as `constants.js` in the `src` directory

This file though is in the `db` folder inside `src`

And all the environment variables are in the `.env` file

after this, export this function and import it in the `index.js` file and use it
