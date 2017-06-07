# COMMENTS

---

在 SQL 中，我們可以加上註解以增加可讀性。

## 單一註解：

```
--Select all:
SELECT * FROM Customers;
```

or

```
#Select all:
SELECT * FROM Customers;
```

## 多行註解：

```
SELECT * FROM Customers WHERE (CustomerName LIKE 'L%'
OR CustomerName LIKE 'R%' /*OR CustomerName LIKE 'S%'
OR CustomerName LIKE 'T%'*/ OR CustomerName LIKE 'W%')
AND Country='USA'
ORDER BY CustomerName;
```

or

```
/*Select all the columns
of all the records
in the Customers table:*/
SELECT * FROM Customers;
```



