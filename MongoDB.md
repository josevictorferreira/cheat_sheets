
Dumping a remote database to a specific folder gzipped:

```bash
mongodump --host remote-host.com --db remote_db --gzip --out dump_2022-04-27.gz
```

Restoring the database folder to a local mongodb:

```bash
mongorestore --gzip --db new_mongo_database database_folder
```