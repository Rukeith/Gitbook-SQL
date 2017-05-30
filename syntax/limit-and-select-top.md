# LIMIT & SELECT TOP

---

主要用來限定回傳資料後的資料數，有些支援 `SELECT TOP` 有些則叫做 `LIMIT`。

SELECT TOP：

```
SELECT TOP 3 * FROM Customers;
```

LIMIT：

```
SELECT * FROM Customers
LIMIT 3;
```



