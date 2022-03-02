# Postgres Administration

## Backup


### Dump from remote server
```bash
pg_dump -h <REMOTE_HOST> -p <PORT> -U <USER> -f backup_file_name.bak DATABASE_NAME 
```

### Dump local
```bash
pg_dump -c -C -F p -f backup_file_name.bak.sql DATABASE_NAME
```


## Restore


### Restore from backup file (.sql)
```bash
psql -U username -f filename.sql
```

### Restore from custom archive backup file (.bak)
```bash
pg_restore -d db_name /path/to/your/file/db_name.bak -c -U db_user
```

--------------

## User

### List Users
```bash
\du
```

### Set/Reset postgres user password
```bash
\password username
```

### Create user
```bash
create user USER_NAME with encrypted password 'mypassword';
```

### Grant privileges
```bash
grant all privileges on database DATABASE to USER_NAME;
```

### Delete user
```bash
DROP USER [ IF EXISTS ] USER_NAME [, ...]
```