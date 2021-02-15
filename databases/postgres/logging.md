# Logging

Inside the _**postgresql.conf**_ file you can enable postgresql logs changing:

```text
log_statement = 'all'
log_filename = 'postgresql-%Y-%m-%d_%H%M%S.log'
logging_collector = on
sudo service postgresql restart
#Find the logs in /var/lib/postgresql/<PG_Version>/main/log/
#or in /var/lib/postgresql/<PG_Version>/main/pg_log/
```

