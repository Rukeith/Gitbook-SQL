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

如果 GROUP BY 使用多個欄位的話，會先以第一個為主，再去排序第二個。

```
SELECT rating, rental_rate, count(film_id)
FROM film
GROUP BY rating, rental_rate;
```

可以看到下面的結果，會先排序  rating 欄位之後，才依照 rental\_rate 排序。

![](/assets/Screen Shot 2017-06-20 at 14.18.00.png)



