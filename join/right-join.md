# Right Join

---

The RIGHT JOIN keyword returns all records from the right table \(table2\), and the matched records from the left table \(table1\). The result is NULL from the left side, when there is no match.

在某些資料庫上 Right Join 會叫做 Right Outer Join。

![](/assets/img_rightjoin.gif)  


操作：

```
SELECT Orders.OrderID, Employees.LastName, Employees.FirstName
FROM Orders
RIGHT JOIN Employees ON Orders.EmployeeID = Employees.EmployeeID
ORDER BY Orders.OrderID;
```



