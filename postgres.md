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