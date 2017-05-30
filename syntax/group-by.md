# GROUP BY

---

`GROUP BY`  指令常用來跟函數一起使用（COUNT, MAX, MIN, SUM, AVG），將資料包成一個或多個欄位。效果上跟 DISTINCT 有點相似。

Demo database：

| Store\_Name | Sales | Txn\_Date |
| :--- | :--- | :--- |
| Los Angeles | 1500 | 05-Jan-1999 |
| San Diego | 250 | 07-Jan-1999 |
| Los Angeles | 300 | 08-Jan-1999 |
| Boston | 700 | 08-Jan-1999 |

指令：

```
SELECT Store_Name, SUM(Sales) 
FROM Store_Information 
GROUP BY Store_Name;
```

結果：

| Store\_Name | SUM\(Sales\) |
| :--- | :--- |
| Los Angeles | 1800 |
| San Diego | 250 |
| Boston | 700 |



