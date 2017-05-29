# Column

---

## INSERT INTO 新增資料

```
INSERT INTO Store_Information (Store_Name, Sales, Txn_Date)
VALUES ('Los Angeles', 900, 'Jan-10-1999');
```

## UPDATE 更新資料

這裡要注意的是，如果沒有 WHERE 條件，則全部的資料都會被更新。

```
UPDATE Store_Information
SET Sales = 500
WHERE Store_Name = 'Los Angeles' 
AND Txn_Date = 'Jan-08-1999';
```

## DELETE 刪除資料

以下會刪除所有 Store\_Name 是 Los Angeles 的資料

```
DELETE FROM Store_Information
WHERE Store_Name = 'Los Angeles';
```

這邊也要注意，如果沒有 WHERE，則全部資料都會被刪除

```
DELETE FROM table_name;
```

or

```
DELETE * FROM table_name;
```



