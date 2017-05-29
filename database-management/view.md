# View

---

View 可以被當作是虛擬表格。它跟表格的不同是，表格中有實際儲存資料，而視觀表是建立在表格之上的一個架構，它本身並不實際儲存資料。不能包含 `ORDER BY`。

## CREATE VIEW 建立 View

View "Current Product List" 會從 Product 資料表列出所有為停產的產品。由以下指令建立：

```SQL
CREATE VIEW [Current Product List] AS
SELECT ProductID, ProductName
FROM Products
WHERE Discontinued = No;
```

建立後，之後都可以使用以下指令來得到資料：

```
SELECT * FROM [Current Product List];
```

若現在想取得所有價格高於平均價高的產品，可以由以下指令建立：

```
CREATE VIEW [Products Above Average Price] AS
SELECT ProductName, UnitPrice
FROM Products
WHERE UnitPrice > (SELECT AVG(UnitPrice) FROM Products);
```

建立 View 時也可以從另一個 View 來建立，例如我現在要從 "Product Sales for 1997" 的 View，建立一個計算每個 Category 的銷售總合：

```
CREATE VIEW [Category Sales For 1997] AS
SELECT DISTINCT CategoryName, Sum(ProductSales) AS CategorySales
FROM [Product Sales for 1997]
GROUP BY CategoryName;
```

## 更新 View

可以使用以下指令來更新 View（其實就是建立一個新的來取代）

```SQL
CREATE OR REPLACE VIEW [Current Product List] AS
SELECT ProductID, ProductName, Category
FROM Products
WHERE Discontinued = No;
```

## DROP VIEW 刪除 View

```
DROP VIEW view_name;
```

## SHOW CREATE VIEW 顯示 View 的建立指令

```
SHOW CREATE VIEW view_name
```

範例：

    mysql> SHOW CREATE VIEW v;
    +------+----------------------------------------------------+
    | View | Create View                                        |
    +------+----------------------------------------------------+
    | v    | CREATE VIEW `test`.`v` AS select 1 AS `a`,2 AS `b` |
    +------+----------------------------------------------------+



