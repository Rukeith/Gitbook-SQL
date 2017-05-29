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

包含了 NOT NULL 和 UNIQUE 的特性。每個資料表只能有一個 Primary key，可以是原本資料中的一個欄位，或是多個欄位組合出來的（稱為 Composite Key）。

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

由一個\(或數個\)指向另外一個資料表 Primary key 的欄位。

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



