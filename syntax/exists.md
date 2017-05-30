# EXISTS

---

`EXISTS` 是用來測試內查詢有沒有產生任何結果。如果有的話，系統就會執行外查詢中的 SQL。若是沒有的話，那整個 SQL 語句就不會產生任何結果。

```
SELECT SUM(Sales) FROM Store_Information
WHERE EXISTS
(SELECT * FROM Geography
WHERE Region_Name = 'West');
```

以下指令當 suppliers 列表有 product price 等於 22 時 SQL 會回傳 True：

```
SELECT SupplierName
FROM Suppliers
WHERE EXISTS (SELECT ProductName FROM Products WHERE SupplierId = Suppliers.supplierId AND Price = 22);
```



