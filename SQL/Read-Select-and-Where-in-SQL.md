# READ, SELECT, and WHERE in SQL

So what if you want to read some data from a table in sql

you can do that with the `SELECT` command

for example, you would want to read all the data from the products table

```sql
SELECT * FROM products
```

here `*` means all

Now if you want to do a more refined search, like search for a product whose price is 1.20, then you would need to use the `WHERE` command as well

```sql
SELECT * FROM products
WHERE price = 1.20
```

Now this will filter out the products having price 1.20.

You can do this with any field like, id or name
