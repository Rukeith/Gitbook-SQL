# Data Type 資料型態 {#data-type}

---

因為不同的 SQL Server 資料型態會有些許的差異，所以還是要以所使用的 SQL Server 為準。 一般來說，資料型態可以分成三種：Numeric、Character、Date & Time。其中空值不等於空格或空白，使用 `NULL` 表示空值。以下是一般常見的資料型態：

## Text type

| 資料類型 | 描述 |
| :--- | :--- |
| CHAR\(size\) | 儲存固定長度的字串（包含字母、數字和特殊符號）。在括號中指定字串的長度，最多可達 255 個字串。 |
| VARCHAR\(size\) | 儲存變動長度的字串（包含字母、數字和特殊符號）。在括號中指定字串的長度，最多可達 255 個字串。Note：如果超過 255 會轉成 TEXT 型態 |
| TINYTEXT | 儲存最大長度 255 個字符的字串 |
| TEXT | 儲存最大長度 65,535 個字符的字串 |
| MEDIUMTEXT | 儲存最大長度 16,777,215 個字符的字串 |
| LONGTEXT | 儲存最大長度 4,294,967,295 個字符的字串 |
| TINYBLOB | 用於 BLOBs \(Binary Large OBjects\)。儲存最多 255 bytes 的資料 |
| BLOB | 用於 BLOBs \(Binary Large OBjects\)。儲存最多 65,535 bytes 的資料 |
| MEDIUMBLOB | 用於 BLOBs \(Binary Large OBjects\)。儲存最多 16,777,215 bytes 的資料 |
| LONGBLOB | 用於 BLOBs \(Binary Large OBjects\)。儲存最多 4,294,967,295 bytes 的資料 |
| BINARY\(n\) | 儲存固定長度的二進制字串 |
| VARBINARY\(n\) | 儲存變動長度的二進制字串 |
| ENUM | 允許輸入可能值得列表。可以在 ENUM 列表中列出最大 65,535 個值。如果列表中不存在插入的值，則會插入空值。Note：這些值會按照輸入的順序儲存。可以按照此格式輸入可能的值：ENUM\('X','Y','Z'\) |
| SET | 類似於 ENUM，但 SET 最多只能包含 64 個列表。但可以儲存一個以上的值。 |

## Number type

這些類型擁有額外的屬性 `UNSIGNED`。通常整數可以是負數或整數，如果添加了 `UNSIGNED` 屬性，則範圍將從 0 開始，而不包含負數。

| 資料類型 | 描述 |
| :--- | :--- |
| TINYINT\(size\) | 一般是 -128 ~ 127，如果是 UNSIGNED 則為 0 ~ 255。在括弧內設定最大值。 |
| SMALLINT\(size\) | 一般是 -32768 ~ 32767，如果是 UNSIGNED 則為 0 ~ 65535。在括弧內設定最大值。 |
| MEDIUMINT\(size\) | 一般是 -8388608 ~ 8388607，如果是 UNSIGNED 則為 0 ~ 16777215。在括弧內設定最大值。 |
| INT\(size\) | 一般是 -2147483648 ~ 2147483647，如果是 UNSIGNED 則為 0 ~ 4294967295。在括弧內設定最大值。 |
| BIGINT\(size\) | 一般是 -9223372036854775808 ~ 9223372036854775807，如果是 UNSIGNED 則為 0 ~ 18446744073709551615。在括弧內設定最大值。 |
| FLOAT\(size, d\) | 帶有浮點數的小數值。在括弧內設定最大位數。在 d 參數中設定小數點最大到幾位。 |
| DOUBLE\(size, d\) | 帶有浮點數的大數值。在括弧內設定最大位數。在 d 參數中設定小數點最大到幾位。 |
| DECIMAL\(size, d\) | 將 DOUBLE 類型作為字串儲存的類型，可以設定固定的小數點。在括弧內設定最大位數。在 d 參數中設定小數點最大到幾位。 |

## Date & Time type

即使 `DATETIME` 和 `TIMESTAMP` 回傳相同的格式，但是處理方式不同。在 `INSERT` 或 `UPDATE` 查詢中，`TIMESTAMP` 會自動將自己設定為當前的日期和時間。`TIMESTAMP` 也可以接受不同的格式，如： `YYYYMMDDHHMMSS`、`YYMMDDHHMMSS`、`YYYYMMDD` 或  `YYMMDD`。

| 資料類型 | 描述 |
| :--- | :--- |
| DATE | 格式：YYYY-MM-DD。Note：支持的範圍 '1000-01-01' ～ '9999-12-31'。 |
| DATETIME | 日期和時間的組合類型。格式：YYYY-MM-DD HH:MI:SS。Note：支持的範圍 '1000-01-01 00:00:00' ～ '9999-12-31 23:59:59'。 |
| TIMESTAMPS | 時間戳。使用 Unix epoch \('1970-01-01 00:00:00' UTC\) 的描述來儲存。 格式：YYYY-MM-DD HH:MI:SS。Note：支持的範圍 '1970-01-01 00:00:01' UTC ～ '2038-01-09 03:14:07' UTC |
| TIME | 時間。格式：HH:MI:SS。Note：支持的範圍 '-838:59:59' ～ '838:59:59'。 |
| YEAR | 2 位或 4 位格式的年。Note: 4 位格式允許的值的格式：1901 ～ 2155。2 位格式允許的值的格式：70 ～ 69，表示 1970 ～ 2069。 |

## 快速參考

| **Data type** | **Access** | **SQLServer** | **Oracle** | **MySQL** | **PostgreSQL** |
| :--- | :--- | :--- | :--- | :--- | :--- |
| boolean | Yes/No | Bit | Byte | N/A | Boolean |
| integer | Number \(integer\) | Int | Number | Int Integer | Int Integer |
| float | Number \(single\) | Float Real | Number | Float | Numeric |
| currency | Currency | Money | N/A | N/A | Money |
| string \(fixed\) | N/A | Char | Char | Char | Char |
| string \(variable\) | Text \(&lt;256\) Memo \(65k+\) | Varchar | Varchar Varchar2 | Varchar | Varchar |
| binary object | OLE Object Memo | Binary \(fixed up to 8K\) Varbinary \(&lt;8K\) Image \(&lt;2GB\) | Long Raw | Blob Text | Binary Varbinary |



