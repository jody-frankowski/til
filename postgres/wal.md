# Write Ahead Logs

Wal files are an important concept in postgres. They are used in archiving
and replication for example. What they actually contain is quite interesting.
Contrary to what some may think, they do not contain the sql queries, they
only contain the results of those.

[This presentation at the pgcon 2012](https://www.pgcon.org/2012/schedule/attachments/258_212_Internals%20Of%20PostgreSQL%20Wal.pdf)
goes over the internals of Postgres' WAL.
On page 7 on you can see some examples of the conversion between sql
queries and WALs.

For example if there is the following sql query:

```sql
DELETE FROM score WHERE team = 'AUS';
```

It will be converted to:

```
Header Info : crc,
RM_HEAP_ID, Xid,len,
XLOG_HEAP_DELETE

Data: tupleid
```
