# Column

---

## INSERT INTO 新增資料

```
-- 需要指定插入的欄位
INSERT INTO Store_Information (Store_Name, Sales, Txn_Date)
VALUES ('Los Angeles', 900, 'Jan-10-1999');

-- 一次插入多筆資料
INSERT INTO students(full_name,gender,age)
VALUES
('德莱厄斯','男','25'),
('寡妇收割者','女',22),
('光辉女神','女',18),
('赵信','男',21),
('曙光女神','女','22');
```

如果沒有指定插入資料的欄位，則會需要填入所有的資料

```
INSERT INTO students
VALUES (20170001,'盖伦','男','24');
```

### INSERT INTO SELECT

從一個資料表複製資料到另一個資料表，需要欄位的資料類型一致才行。對於已存在的資料將不受影響。此功能跟 `SELECT INTO` 很像，詳細內容在 `SELECT` 篇章介紹。簡單說這樣的寫法會插入搜尋出來的資料。

```
INSERT INTO Customers (CustomerName, City, Country)
SELECT SupplierName, City, Country FROM Suppliers
WHERE Country='Germany';
```

## UPDATE 更新資料

這裡要注意的是，如果沒有 `WHERE` 條件，則所有資料的該欄位都會被更新。

```
UPDATE Store_Information
SET Sales = 500
WHERE Store_Name = 'Los Angeles' 
AND Txn_Date = 'Jan-08-1999';
```

下面指令則可以把 name 欄位的資料都寫到 description 欄位

```
UPDATE link
SET description = name;
```

## DELETE 刪除資料

DELETE 會回傳被刪除資料的數量。

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



