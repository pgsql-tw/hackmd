# 取得資料庫物件所佔用的磁碟空間
## 參閱
- [9.26.7. Database Object Management Functions](https://docs.postgresql.tw/the-sql-language/functions-and-operators/system-administration#9-26-7-database-object-management-functions)
## pg_relation_size()
- 結果的單位是 Byte

```
select pg_relation_size('mytable');

pg_relation_size
------------------
            16384
```
## pg_size_pretty()
- 可以將空間大小的數目轉換為易於閱讀的方式顯示
```
SELECT pg_size_pretty (pg_relation_size('mytable'));

pg_size_pretty
----------------
 16 KB

```
- 會自動以 KB, MB, GB 等單位轉換顯示

## pg_database_size()
- 適合用來監控資料庫所佔用的空間大小
```
select pg_size_pretty(pg_database_size ('postgres'));

 pg_size_pretty
----------------
 8517 MB
```