# Syntax tricks

## Alternatives for quotes

{% embed url="https://book.hacktricks.xyz/pentesting-web/sql-injection/postgresql-injection\#forbidden-quotes" caption="Workaround when quotes cannot be injected" %}

## Encoding 

Another alternative to circumvent blacklisting or WAFs is to encode our payload, example:

```text
select convert_from(decode('SGVsbG8=', 'base64'), 'utf-8');
# is equal to
select 'hello';
```

