# UNION

---

`UNION` 指令的目的是將兩個 SQL 語句的結果合併起來。`UNION` 跟 `JOIN `有些許類似，因為這兩個指令都可以由多個表格中擷取資料。`UNION` 的一個限制是兩個 SQL 語句所產生的欄位需要是同樣的資料種類。另外，當我們用 `UNION` 這個指令時，我們只會看到不同的資料值 \(類似 `SELECT DISTINCT`\)。如果想要將重複的資料也都顯示出來，則要使用 `UNION ALL`。

## 範例

資料：

Customers：

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1   | Alfreds Futterkiste | Maria Anders | Obere Str. 57 | Berlin | 12209 | Germany |
| 2 | Ana Trujillo Emparedados y helados | Ana Trujillo | Avda. de la Constitución 2222 | México D.F. | 05021 | Mexico |
| 3 | Antonio Moreno Taquería | Antonio Moreno | Mataderos 2312 | México D.F. | 05023 | Mexico |

Suppliers：

| SupplierID | SupplierName | ContactName | Address | City | PostalCode | Country |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | Exotic Liquid | Charlotte Cooper | 49 Gilbert St. | London | EC1 4SD | UK |
| 2 | New Orleans Cajun Delights | Shelley Burke | P.O. Box 78934 | New Orleans | 70117 | USA |
| 3 | Grandma Kelly's Homestead | Regina Murphy | 707 Oxford Rd. | Ann Arbor | 48104 | USA |

操作：

```
SELECT City, Country FROM Customers
WHERE Country='Germany'
UNION
SELECT City, Country FROM Suppliers
WHERE Country='Germany'
ORDER BY City;
```

結果：

| City | Country |
| :--- | :--- |
| Aachen | Germany |
| Berlin | Germany |
| Brandenburg | Germany |
| Cunewalde | Germany |
| Cuxhaven | Germany |
| Frankfurt | Germany |
| Frankfurt a.M. | Germany |
| Köln | Germany |
| Leipzig | Germany |
| Mannheim | Germany |
| München | Germany |
| Münster | Germany |
| Stuttgart | Germany |



