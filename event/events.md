# EVENTS

---

幾個事務處理常見的術語

事務（transaction）： 指一組 SQL 語句

回退（rollback）： 指撤銷指定 SQL 語句的過程

提交（commit）： 指將未存儲的 SQL 語句結果寫入到數據庫表

保留點（savepoint）： 指事務處理中設置的臨時佔位符，你可以對它發布回退（這個回退與回退整個事務處理不同）

