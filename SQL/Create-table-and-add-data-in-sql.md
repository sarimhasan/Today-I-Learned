# Create table and Insert data in SQL

So for this basic demo, I am going to use a website known as sqliteonline.com

In sql language, you can create a database and define its properties like this

```sql
CREATE TABLE products (
	id INT NOT NULL,
	name STRING,
	price smallmoney,
	PRIMARY KEY (id)
)
```

Now if you run this, you will see that you now have a table named as products

the data type of id is integer and `NOT NULL` says that you can't have the id as NULL or empty as we are going to use it as the primary key

primary keys are a unique identifier that you can use to call the entire row

then you have name property and its data type as string

lastly, price as its type as smallmoney, smallmoney is a predefined type in sql

Now if you want to add a new entry you can run the following commands, if you know all the values of all the properties

```sql
INSERT INTO products
VALUES (1, "Pen", 1.20)
```

You need to first specify the command i.e. `INSERT` in this case

then `INTO`, to specify the name of the table afterwards

then in the next line without entering a coma in the first, enter the value in brackets by first entering the `VALUES` keyword

this will create a new data entry in your table

Now if you want to enter the value for only 2 fields, let's say you want to add the second item "pencil" but don't know the price yet, you can do it like this

by first writing `INSERT` and then `INTO` and the table name, you need to specify the value in brackets

then in the second line by saying `VALUES`, you can add the value of the 2 or more fields defined above

```sql
INSERT INTO newProducts (id, name)
VALUES (2, "Pencil")
```
