# AVG & COUNT & SUM

---

* AVG：計算該欄位的平均值
* COUNT：計算該欄位的資料總數
* SUM：計算該欄位的總和

AVG：

```
SELECT AVG(Price)
FROM Products;
```

COUNT：

```
SELECT COUNT(ProductID)
FROM Products;
```

`COUNT` 和 `DISTINCT` 經常被合起來使用，目的是找出表格中有多少筆不同的資料。

```
SELECT COUNT (DISTINCT Store_Name) 
FROM Store_Information;
```

SUM：

```
SELECT SUM(Quantity)
FROM OrderDetails;
```



