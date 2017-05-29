# Index

---

索引 \(Index\) 可以幫助我們從表格中快速地找到需要的資料。如果一個表格沒有索引的話，資料庫系統就需要將整個表格的資料讀出 \(這個過程叫做 Table Scan\)。若有適當的索引存在，資料庫系統就可以先由這個索引去找出需要的資料是在表格的什麼地方，然後直接去那些地方抓資料。這樣子速度就快多了。

索引的命名並沒有一個固定的方式。通常會用的方式是在名稱前加一個字首，例如 "`IDX_`" ，來避免與資料庫中的其他物件混淆。另外，在索引名之內包括表格名及欄位名也是一個好的方式。每個資料庫會有它本身的 `CREATE INDEX` 語法，而不同資料庫的語法會有不同。因此，在下指令前，請先由資料庫使用手冊中確認正確的語法。

索引的缺點是會需要一定的硬碟空間來儲存，當資料量大時會降低寫入該欄位的效率。

## CREATE INDEX 建立索引

```
CREATE INDEX IDX_CUSTOMER_LOCATION ON Customer (City, Country);
or
# Creates a unique index on a table. Duplicate values are not allowed
CREATE UNIQUE INDEX index_name ON table_name (column_name);
```

## DROP INDEX 刪除索引

因為索引一定會儲存於一個資料表中，所以如果把資料表刪除，索引也會跟著刪除掉。

```
DROP INDEX emp_last_index ON employees;
```



