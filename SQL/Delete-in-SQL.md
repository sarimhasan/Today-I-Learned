# Delete in SQL

We have this table named as products

| id  | name   | price | stock |
| --- | ------ | ----- | ----- |
| 1   | Pen    | 1.20  | 32    |
| 2   | Pencil | 0.80  | 12    |
| 3   | Rubber | 1.00  | 40    |

Here is how you can [CREATE Table and INSERT data in SQL](https://github.com/sarimhasan/Today-I-Learned/blob/main/SQL/Create-table-and-add-data-in-sql.md)

So what if you want to say that you don't sell pencils anymore

you can just delete the pencil's row from your table

by using the `DELETE` command followed by `FROM` and then your table name

and then specify which row to delete by using the `WHERE` command

```sql
DELETE FROM products
WHERE id = 2
```
