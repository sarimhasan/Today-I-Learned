# How to CRUD in MongoDB

# Create

to create a new database you can just use the `use` command followed by the database name. `use school`

to create a new document in a new collection, use this command: `db.collectionName.insertOne()`

to insert one document, use `insertOne()`, to insert many documents, use `insertMany()`.

Inside insert, use curly brackets to define the field name and its value. Use comma to separate multiple values. For example, inside the school database, `db.students.insertOne({name: "Sarim", age: 17, gpa: 3.7})`

this would create a new document with a unique id and all the data you provided inside the students collection

Like this you can use `insertMany()`.

```js
db.students.insertMany(
  { name: 'Aayan', age: 15, gpa: 2.8 },
  { name: 'Hussain', age: 20, gpa: 1.9 }
);
```

# Read

If you want to read some data, you can use the find command with some filters to specify your search result

for example, `db.students.find()`, this will give you all of the documents as json objects

You can also use the `findOne()` command to find the first object/document

this find method accepts two objects. one is the query and the second one is projection

`find( {query}, {projection} )`

## Query

meaning you can specify a query like, find all the students with the gpa of 2.8: `db.students.find( { gpa: 2.8 } )`

This will give you the document for Ayan and other students if you have any having the gpa of 2.8

## Projection

Now what if you want to filter out the fields of the documents, for example, you don’t want to see the id field or any other

So, let’s say you don’t want to see the id field along with the age and you only wan to see the gpa and name

```js
db.students.find({}, { _id: false, age: false });
```

this will give you all the documents of students excluding the id and age fields.

and yes, you can use the query object along with the projection to more filter out your search

# Update

if you want to update a document, what you would want to do?

first, you would want to find that document and then update a property

so to find a property we would do it like the find method but with `updateOne()` or `updateMany()`

in the first object, you would have to select/find the object using the query method and in the second object you would use the `$set` operator to set a property in a document

for example, to add a property of `fullTime` to all the documents which would be a Boolean value, we will do this

```js
db.students.updateMany({}, { $set: { fullTime: false } });
```

now to set this value as true to the document which has a name of “Sarim”, you will do something like this:

```js
db.students.updateOne({ name: 'Sarim' }, { $set: { fullTime: true } });
```

# Delete

delete is very similar to the update command, where you have to select the document which you would like to delete by using the `deleteOne()` or `deleteMany()`

to delete a document which have a gpa of 2.8, you can do it like this:

```js
db.students.deleteOne({ gpa: 2.8 });
```

So this would delete one document having the gpa of 2.8

and you can do a similar thing with the `deleteMany()` command
