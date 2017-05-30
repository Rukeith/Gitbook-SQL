# AS

---

SQL 允許我們給 Table 和 Column 設定別名，以方便我們記憶和使用。`AS`** **是用來指定欄位別名或是表格別名的。放在欄位名和欄位別名之間，或是放在表格名和表格別名之間。

```
SELECT A1.Store_Name AS Store, SUM(A1.Sales) AS 'Total Sales'
FROM Store_Information AS A1
GROUP BY A1.Store_Name;
```

結果：

| Store | Total Sales |
| :--- | :--- |
| Los Angeles | 1800 |
| San Diego | 250 |
| Boston | 700 |

有些服務支援更簡便的寫法，不用加 AS 直接在名稱後面空一格即可。

```
SELECT A1.Store_Name Store, SUM(A1.Sales) 'Total Sales'
FROM Store_Information A1
GROUP BY A1.Store_Name;
```



