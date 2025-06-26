# Github-Actions-Study
Estudio para certificacion de Github Actions

## Services Examples✅

### MySQL Services example

```yml
mysql:
  image: mysql:latest
  env:
    MYSQL_ROOT_PASSWORD: root
    MYSQL_DATABASE: testdb
  ports:
    - 3306:3306
```

### Redis Services example

```yml
 redis:
  image: redis:latest
  ports:
    - 6379:6379
```

### Postgres Services example

```yml
postgres:
  image: postgres:latest
  env:
    POSTGRES_USER: dev
    POSTGRES_PASSWORD: dev
    POSTGRES_DB: dev
  ports:
    - 5432:5432
```

### MsSQL Services example

```yml
mssql:
    image: mcr.microsoft.com/mssql/server:2017-latest
    env:
      ACCEPT_EULA: Y
      SA_PASSWORD: "yourStrong(!)Password"
      MSSQL_PID: Express
    ports:
      - 1433:1433
```

### Oracle Services example

```yml
oracle:
    image: sath89/oracle-12c
    ports:
      - 1521:1521
```

## Environment variable example

```yaml
 env:
      NAME_DEV: Dc Dev
```

## Environment variable for the Github environment

```yml
  ${{ vars.DEV_NAME }}
```

## Environment variable for the Github environment secret

```yml
  ${{ secrets.NAME_DEV }}
```
