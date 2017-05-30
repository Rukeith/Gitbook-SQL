* [ ] # Inner Join

---

使用 INNER JOIN 來取得符合兩邊資料表的資料

![](/assets/img_innerjoin.gif)

## 範例

Orders 資料表

| OrderID | CustomerID | EmployeeID | OrderDate | ShipperID |
| :--- | :--- | :--- | :--- | :--- |
| 10308 | 2 | 7 | 1996-09-18 | 3 |
| 10309 | 37 | 3 | 1996-09-19 | 1 |
| 10310 | 77 | 8 | 1996-09-20 | 2 |

Customers 資料表

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1   | Alfreds Futterkiste | Maria Anders | Obere Str. 57 | Berlin | 12209 | Germany |
| 2 | Ana Trujillo Emparedados y helados | Ana Trujillo | Avda. de la Constitución 2222 | México D.F. | 05021 | Mexico |
| 3 | Antonio Moreno Taquería | Antonio Moreno | Mataderos 2312 | México D.F. | 05023 | Mexico |

執行：

```
SELECT Orders.OrderID, Customers.CustomerName
FROM Orders
INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID;
```

結果：

| OrderID | CustomerName |
| :--- | :--- |
| 10308 | Ana Trujillo Emparedados yhelados |



連結三個資料表：

```
SELECT Orders.OrderID, Customers.CustomerName, Shippers.ShipperName
FROM ((Orders
INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID)
INNER JOIN Shippers ON Orders.ShipperID = Shippers.ShipperID);
```



