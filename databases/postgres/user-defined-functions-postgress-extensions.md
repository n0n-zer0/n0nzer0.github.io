# User Defined functions \(postgress extensions\)



{% embed url="https://book.hacktricks.xyz/pentesting-web/sql-injection/postgresql-injection/rce-with-postgresql-extensions" %}

Import here is that you compile the ".SO" file with the correct headers. You do not have to install that exact postgres version for this! You can simple unpack the source and point to the correct header files: [https://www.postgresql.org/ftp/source/](https://www.postgresql.org/ftp/source/) 

```text
gcc lib_postgresqludf_sys.c -I/postgresql-10.0/src/include -fPIC -shared -o udf64.so
```



