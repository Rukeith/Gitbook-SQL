# ORDER BY

---

我們在取得資料後，有時候會需要將資料做排序，利用價格排序之類的。`ORDER BY` 可以幫助我們依照欄位來做正序或反序排列。`ORDER BY` 後在接上要用來排序的欄位（可多個且排序不同），預設上是使用 `ASC` 排序。`ASC` 代表結果會以由小往大的順序列出，而 `DESC` 代表結果會以由大往小的順序列出。

```
SELECT * FROM Customers
ORDER BY Country ASC, CustomerName DESC;
```



