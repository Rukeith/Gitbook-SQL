# WHERE

---

一般正常的使用情境上，並不會把所有的資料都取出來。所以我們就會需要添加一些篩選條件，這邊就會使用到了 WHERE。

```
SELECT Store_Name 
FROM Store_Information 
WHERE Sales > 1000;
```

上面是個很簡單的例子，但是在商業上的邏輯有時候是多種的。下面會介紹其他的邏輯的運算子。

## AND

```
SELECT * FROM Customers
WHERE Country='Germany' AND City='Berlin';
```

## OR

```
SELECT * FROM Customers
WHERE City='Berlin' OR City='München';
```

## NOT

```
SELECT * FROM Customers
WHERE NOT Country='Germany';
```

## IN

我們事先已知道至少一個我們需要的值，而我們將這些知道的值都放入 `IN`** **這個子句。

```
SELECT * FROM Customers
WHERE Country NOT IN ('Germany', 'France', 'UK');
```

## BETWEEN

讓我們可以運用一個範圍 \(range\) 內抓出資料庫中的值。

```
SELECT * FROM Products
WHERE Price NOT BETWEEN 10 AND 20;
```

## Subquery

我們也可以在  WHERE 裡面再多加一層的 Query。只需要用括弧刮起來。

```
SELECT title, rental_rate
FROM film
WHERE rental_rate > (SELECT AVG(rental_rate) FROM film);
```



