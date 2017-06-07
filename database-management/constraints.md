# Constraints

---

Constraints 用來指定資料表中資料的規則。Constraints 有兩種層級：Column level 和 Table level。Table level 的會涵蓋到整個 Table，Column level 只會限定該 Column。可以在建立 Table 時設定，也可以之後修改 Table 時更新上去。以下列出幾個常見的 Constraints：

## NOT NULL 非空值

預設上，Column 可以儲存 NULL 值。此 Constraints 限定該 Column 不能儲存 NULL 值。

```
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255) NOT NULL,
    Age int
);
```

## UNIQUE 唯一值

用來確保該欄位的資料都是不一樣的

```
CREATE TABLE Customer 
(SID integer UNIQUE, 
Last_Name varchar (30), 
First_Name varchar(30));
```

## PRIMARY KEY 主鍵

包含了 `NOT NULL` 和 `UNIQUE` 的特性。每個資料表只能有一個 Primary key，可以是原本資料中的一個欄位，或是多個欄位組合出來的（稱為 Composite Key），不能更改。

* 用於識別資料表中的單獨的一行、確保了唯一性
* 用於跟另外的資料表作關聯
* 一般會自動預設建立索引，提高搜尋速度

```
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    CONSTRAINT PK_Person PRIMARY KEY (ID,LastName)
);
```

## FOREIGN KEY 外來鍵

由一個\(或數個\)指向另外一個資料表 Primary key 的欄位。 A 資料表中的某個字段，同時也是 B 資料表中的 Primary key。這個字段就是 A 資料表的 Foreign key。

* 其相互連結的資料表需要是使用同樣的儲存方式，不能使用 View。且資料表的儲存只能使用 InnoDB。
* 兩個欄位的資料型態需要是一樣的，長度可以不同。
* 需要建立 Index，如果沒有建立會自動建立。

```
CREATE TABLE Orders (
    OrderID int NOT NULL PRIMARY KEY,
    OrderNumber int NOT NULL,
    PersonID int FOREIGN KEY REFERENCES Persons(PersonID)
);
```

## CHECK 檢查

確保一個欄位中的所有資料都是符合某些條件。

```
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int CHECK (Age>=18)
);
```

更新

```
ALTER TABLE Persons
ADD CONSTRAINT CHK_PersonAge CHECK (Age>=18 AND City='Sandnes');
```

刪除

```
ALTER TABLE Persons
DROP CONSTRAINT CHK_PersonAge;
```

## DEFAULT 預設值

```
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    City varchar(255) DEFAULT 'Sandnes'
);
```

更新

```
ALTER TABLE Persons
ALTER COLUMN City SET DEFAULT 'Sandnes';
```

刪除

```
ALTER TABLE Persons
ALTER COLUMN City DROP DEFAULT;
```

### DEFAULT CHARACTER SET

用於設定資料庫的 Table 使用的字符集，如無設定就使用預設值。

```SQL

CREATE TABLE students_list(
    id         INT          NOT NULL  AUTO_INCREMENT,
    full_name  VARCHAR(10)  NOT NULL,
    gender     VARCHAR(10)  NULL,
    age        INT          NOT NULL  DEFAULT 20,
    PRIMARY KEY(id)
) ENGINE=InnoDB AUTO_INCREMENT=20170001 DEFAULT CHARACTER SET utf8;
-- 根據上面的設定，primary key 預設由 20170001 開始增加
--  其中 ENGINE 是設定使用的資料庫引擎
```

## AUTO\_INCREMENT 自動增量

此 Constraints 允許在新記錄插入資料表時自動生成唯一編號，通常用於 Primary key。預設上從一開始計算，並每次加 1。

```
CREATE TABLE Persons (
    ID int NOT NULL AUTO_INCREMENT=100, 從 100 開始計算
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    PRIMARY KEY (ID)
);
```



