# LIKE

---

在使用 WHERE 時，我們還能使用 LIKE 在做查找。LIKE 可以讓我們使用 pattern 的方式來找尋我們要的資料LIKE 使用兩個 wildcards 來組合條件。一般是不分大小寫的，如果在後面加上 `BINARY` 則會區分大小寫：`LIKE BINARY '%J%S%'`

1. `%`：代表零個、一個、或數個字母。

2. `_`：代表剛好一個字母。

3. `[]`：代表一個字串集，需要符合其中的任意一個字串。

範例：

* 'A\_Z': 所有以 'A' 起頭，另一個任何值的字原，且以 'Z' 為結尾的字串。 'ABZ' 和 'A2Z' 都符合這一個模式，而 'AKKZ' 並不符合 \(因為在 A 和 Z 之間有兩個字元，而不是一個字元\)。
* 'ABC%': 所有以 'ABC' 起頭的字串。舉例來說，'ABCD' 和 'ABCABC' 都符合這個模式。
* '%XYZ': 所有以 'XYZ' 結尾的字串。舉例來說，'WXYZ' 和 'ZZXYZ' 都符合這個模式。
* '%AN%': 所有含有 'AN'這個模式的字串。舉例來說， 'LOS ANGELES' 和 'SAN FRANCISCO' 都符合這個模式。
* '\_AN%'： 所有第二個字母為 'A' 和第三個字母為 'N' 的字串。舉例來說，'SAN FRANCISCO' 符合這個模式，而 'LOS ANGELES' 則不符合這個模式。

```
SELECT * 
FROM Store_Information 
WHERE store_name LIKE '%AN%';
```



```
SELECT * FROM students
WHERE full_name LIKE '[Man][Woman]God';
```



