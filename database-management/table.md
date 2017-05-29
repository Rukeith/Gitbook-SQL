# Table

---

## CREATE 建立資料表

在建立資料表時，就可以設定欄位的資料型態

```SQL
CREATE TABLE Persons (
    PersonID int,
    LastName varchar(255),
    FirstName varchar(255),
    Address varchar(255),
    City varchar(255) 
);
```

使用別的資料表欄位來建立

```SQL
CREATE TABLE suppliers
  AS (SELECT companies.id, companies.address, categories.cat_type
      FROM companies, categories
      WHERE companies.id = categories.id
      AND companies.id > 1000);
```

## ALTER 修改資料表結構

### ADD 新增欄位

```
ALTER TABLE Customer ADD Gender char(1);
```

### DROP 刪除欄位

```
ALTER TABLE Customer DROP Gender;
```

### CHANGE 改變欄位名稱

```
ALTER TABLE Customer CHANGE Address Addr char(50);
```

### MODIFY 更改欄位資料型態

```
ALTER TABLE Customer MODIFY Addr char(30);
```

## TRUNCATE 清空資料表

此指令與 Drop 不同的地方在於，只會清空資料，結構都還是保留著

```
TRUNCATE TABLE tablename;
```

## DROP 刪除資料表

```
DROP TABLE tablename;
```



