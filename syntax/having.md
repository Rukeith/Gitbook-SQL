# HAVING

---

`HAVING` 指令被用來對函數產生的值設定條件，通常是在 SQL 的最後一句。不一定需要搭配 `GROUP BY`，如果 `SELECT` 裡面只有函數值，則不需要 `GROUP BY`。個人覺得可以把這當作 `WHERE` 使用。

若我們要找出 Sales 大於 1,500 的 Store\_Name：

```
SELECT Store_Name, SUM(Sales) 
FROM Store_Information 
GROUP BY Store_Name
HAVING SUM(Sales) > 1500;
```



