# Column

---

## INSERT INTO 新增資料

```
INSERT INTO Store_Information (Store_Name, Sales, Txn_Date)
VALUES ('Los Angeles', 900, 'Jan-10-1999');
```

### INSERT INTO SELECT

從一個資料表複製資料到另一個資料表，需要欄位的資料類型一致才行。對於已存在的資料將不受影響。此功能跟 `SELECT INTO` 很像，詳細內容在 `SELECT` 篇章介紹。

```
INSERT INTO Customers (CustomerName, City, Country)
SELECT SupplierName, City, Country FROM Suppliers
WHERE Country='Germany';
```

## UPDATE 更新資料

這裡要注意的是，如果沒有 `WHERE` 條件，則全部的資料都會被更新。

```
UPDATE Store_Information
SET Sales = 500
WHERE Store_Name = 'Los Angeles' 
AND Txn_Date = 'Jan-08-1999';
```

## DELETE 刪除資料

以下會刪除所有 `Store_Name` 是 Los Angeles 的資料

```
DELETE FROM Store_Information
WHERE Store_Name = 'Los Angeles';
```

這邊也要注意，如果沒有 `WHERE`，則全部資料都會被刪除

```
DELETE FROM table_name;
```

or

```
DELETE * FROM table_name;
```



