# Self Join

---

A self JOIN is a regular join, but the table is joined with itself.



資料：

| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1   | Alfreds Futterkiste | Maria Anders | Obere Str. 57 | Berlin | 12209 | Germany |
| 2 | Ana Trujillo Emparedados y helados | Ana Trujillo | Avda. de la Constitución 2222 | México D.F. | 05021 | Mexico |
| 3 | Antonio Moreno Taquería | Antonio Moreno | Mataderos 2312 | México D.F. | 05023 | Mexico |



操作：

```
SELECT A.CustomerName AS CustomerName1, B.CustomerName AS CustomerName2, A.City
FROM Customers A, Customers B
WHERE A.CustomerID <> B.CustomerID
AND A.City = B.City 
ORDER BY A.City;
```

結果：

| CustomerName1 | CustomerName2 | City |
| :--- | :--- | :--- |
| Ana Trujillo Emparedados y helados | Antonio Moreno Taquería | México D.F. |



