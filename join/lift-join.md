# Left Join

---

The LEFT JOIN keyword returns all records from the left table \(table1\), and the matched records from the right table \(table2\). The result is NULL from the right side, if there is no match.

在某些資料庫上 Left Join 會叫做 Left Outer Join。

  
![](/assets/img_leftjoin.gif)



操作：

```
SELECT Customers.CustomerName, Orders.OrderID
FROM Customers
LEFT JOIN Orders ON Customers.CustomerID = Orders.CustomerID
ORDER BY Customers.CustomerName;
```



