# PostgresSQL

Connect PSQL to a remote postgresql host: 
```bash
psql -h remote_host.rds.amazonaws.com -p 5432 -U postgres -W
```

Dump the database using psql:

```bash
pg_dump -h host.com -U postgres -f dump.sql weather_forecast_service_production
```

Restore Dump using psql:

```bash
psql -h localhost -p 5441 -U postgres -d weather_forecast_service_production -f dump.sql
```

Restore Dump of database:

```bash
pg_restore -h localhost -p 5441 -U postgres -c -d weather_forecast_service_production dump.sql
```

Restore dump file with inserts(for better compatibility when dumping for different major versions):

```bash
pg_dump -h host.com -U postgres -f dump.sql weather_forecast_service_production --inserts
```

### Dumping database from Postgresql 14 to Postgresql 12

First, generate the dump of the database:
```bash
pg_dump -h localhost -U postgres --no-acl --no-owner -f georef_measures_service_backup.sql georef_measures_service_production
```
If you wanna dump only insert options from the database:
```bash
pg_dump --column-inserts --data-only --table=<table> <database>
```

After the dump is generated in a plain text ".sql" file, edit the file and add the following to the start:
```sql
GRANT USAGE ON SCHEMA public TO PUBLIC;
```

When using pgcrypto extension, if you receive error with not found function, edit all occurrencies of `gen_random_uuid()` to `public.gen_random_uuid()`.

Lastly, restore your database using your plain text file:

```bash
psql -h localhost -U postgres --set ON_ERROR_STOP=on -d georef_measures_service_production -f georef_measures_service_backup.sql
```