# Syntax

---

SQL 的指令大致可以分為四種：DDL / DML / DCL / TCL。

1. DDL（Data Definition Language）資料定義語言：

    可以建立或修改資料庫本身，如 ALTER 可以修改資料表設計

2. DML（Data Manipulation Language）資料操作語言：

    新增、修改、檢索、刪除資料庫中的資料

3. DCL（Data Control Language）資料控制語言：

    用於維護資料庫的安全

4. TCL（Transaction Control Language）事件控制語言：

# DDL {#ddl-data-definition-language-}

* CREATE 建立物件
* ALTER 修改資料的結構
* DROP 刪除資料
* TRUNCATE - remove all records from a table, including all spaces allocated for the records are removed
* COMMIT - add comments to the data dictionary
* RENAME 重新命名

# DML {#dml}

* SELECT - retrieve data from the a database \(也有說select是DRL: Data Retrieval Language\)
* INSERT - insert data into a table
* UPDATE - updates existing data within a table
* DELETE - deletes all records from a table, the space for the records remain
* MERGE - UPSERT operation \(insert or update\)
* CALL - call a PL/SQL or Java subprogram
* EXPLAIN PLAN - explain access path to data
* LOCK TABLE - control concurrency

# DCL {#dcl}

* GRANT - gives user's access privileges to database
* REVOKE - withdraw access privileges given with the GRANT command

# TCL {#tcl}

* COMMIT - save work done
* SAVEPOINT - identify a point in a transaction to which you can later roll back
* ROLLBACK - restore database to original since the last COMMIT
* SET TRANSACTION - Change transaction options like isolation level and what rollback segment to use



