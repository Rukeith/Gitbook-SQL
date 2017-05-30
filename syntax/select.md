# SELECT

---

從此章節開始會是最重要的部分，因為會相當多種的組合，這邊就要慢慢的講解了。

取得所有欄位資料：

```
SELECT * FROM Customers;
```

取得 CustomerName 和 City 的欄位資料：

```
SELECT CustomerName, City FROM Customers;
```

## DISTINCT

有時候我們不需要重複的資料，則我們可以加上 DISTINCT 來排重

資料：

| Store\_Name | Sales | Txn\_Date |
| :--- | :--- | :--- |
| Los Angeles | 1500 | 05-Jan-1999 |
| San Diego | 250 | 07-Jan-1999 |
| Los Angeles | 300 | 08-Jan-1999 |
| Boston | 700 | 08-Jan-1999 |

```
SELECT DISTINCT Store_Name FROM Store_Information;
```

結果：

| Los Angeles |
| :--- |
| Store\_Name |
| San Diego |
| Boston |

## SELECT INTO

可以複製資料到另一個資料表中

```
SELECT CustomerName, ContactName INTO CustomersBackup2017
FROM Customers;
```



