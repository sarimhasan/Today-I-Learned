# UPDATE single value and ADD Columns in SQL

So in the previous note: [[CREATE Table and INSERT data in SQL]], we created a table with 2 products

1. id = 1, name = "Pen", and price = 1.20
2. id = 2, name = "Pencil" and price = Null

Because at that time we didn't knew the price of the pencil for that we want to sell

## Updating Single Values

Now we know the price is 0.80 pounds

how can we update that in the table?

Its actually easy, first write the `UPDATE` command and after that the name of table

then write the `SET` command and the name and the value of the field

and then specify for which item/row you want to update the value of price by using the `WHERE` command

```sql
UPDATE products
SET price = 0.80
WHERE name = "Pencil"
```

## Adding new Columns

Imagine, now we also need to add how many stock is there for each item

to do that we will need to add a stock field to each of the row, in other words we need to add one more column to the table

In sql lingo, adding or deleting columns is called altering the table or database

So, we will use the `ALTER` command along with the `TABLE` command to specify that it is a table and then the table name

and then the `ADD` command followed by the name of the column and its data type

```sql
ALTER TABLE products
ADD stock INT
```
