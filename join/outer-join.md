# Outer Join

---

Outer Full Join 會回傳符合 Table A 和 Table B 裡面的資料

![](/assets/img_fulljoin.gif)

## 範例

Customers：

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1   | Alfreds Futterkiste | Maria Anders | Obere Str. 57 | Berlin | 12209 | Germany |
| 2 | Ana Trujillo Emparedados y helados | Ana Trujillo | Avda. de la Constitución 2222 | México D.F. | 05021 | Mexico |
| 3 | Antonio Moreno Taquería | Antonio Moreno | Mataderos 2312 | México D.F. | 05023 | Mexico |

Orders：

| OrderID | CustomerID | EmployeeID | OrderDate | ShipperID |
| :--- | :--- | :--- | :--- | :--- |
| 10308 | 2 | 7 | 1996-09-18 | 3 |
| 10309 | 37 | 3 | 1996-09-19 | 1 |
| 10310 | 77 | 8 | 1996-09-20 | 2 |

操作：

```
SELECT Customers.CustomerName, Orders.OrderID
FROM Customers
FULL OUTER JOIN Orders ON Customers.CustomerID=Orders.CustomerID
ORDER BY Customers.CustomerName;
```

結果：

| CustomerName | OrderID |
| :--- | :--- |
| Alfreds Futterkiste |  |
| Ana Trujillo Emparedados y helados | 10308 |
| Antonio Moreno Taquería | 10365 |
|  | 10382 |
|  | 10351 |



