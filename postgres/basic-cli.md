# Basic Command for PostgreSQL

Connect to database

```bash
psql -U username -d database_name -h hostname

# Ex: pgsql -U postgres -d test_db_1 -h localhost
```

List database

```bash
/l

#   Name    |  Owner   | Encoding | Collate |  Ctype  |   Access privileges
# -----------+----------+----------+---------+---------+-----------------------
#  postgres  | postgres | UTF8     | C       | C.UTF-8 |
#  template0 | postgres | UTF8     | C       | C.UTF-8 | =c/postgres   + postgres=CTc/postgres
#  template1 | postgres | UTF8     | C       | C.UTF-8 | =c/postgres   + postgres=CTc/postgres
# (3 rows)
```

Select database

```bash
\c postgres

# You are now connected to database "postgres" as user "postgres".
```

List tables in current database

```bash
\dt

# Did not find any relations.
```

List schemas in current database

```bash
\dn

# public | postgres
```

Show search path

```bash
show search_path;

# search_path
# -------------
# "$user", public
```

Set search path

```bash
SET search_path TO schema_name;

# Ex: SET search_path TO public;

```
