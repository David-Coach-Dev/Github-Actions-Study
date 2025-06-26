# Github-Actions-Study

Estudio para certificación de Github Actions

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

```yml
mkdir -p ~/.ssh
echo " ${{ secrets.SSH_KEY }}" >> ~/.shh/id.rsa
chmod 600 ~/.ssh/id.rsa
ssh-keyscan -H 127.0.1.1 >> ~/.shh/known_hosts
cat ~/.ssh/known_hosts
```

## Conditional if

```yml
- name: deploy
  if: steps.test.outcome == 'success'
  if: failure()
  if: susses()
  if: alwas()
  run: acciones a realizar
```

## Actions Example

### Upload Artifact

```yml
- name: Artifact
  uses: actions/upload-artifact@v4
  if: failure()
  with:
    name: artifacts
    path: |
      package.json
      store/log.log
```

## Rummers

```yml
jobs:
  my server:
    runs-on: self-hosted
  ...
```

## 🎯 ¿Qué hace if: always()?

```yml
- name: "Cleanup SSH keys"
  if: always() # ← Se ejecuta SIEMPRE, sin importar si los steps anteriores fallaron
  run: |
    echo "Limpiando archivos SSH..."
```

Significa: Este step se ejecuta siempre, independientemente de si:

✅ Los steps anteriores fueron exitosos
❌ Los steps anteriores fallaron
⚠️ Los steps anteriores fueron cancelados
📋 Todas las funciones condicionales en GitHub Actions:

### 1. Funciones de estado 🚦

```yml
# Se ejecuta solo si TODO fue exitoso (DEFAULT)
- name: "Success only"
  if: success()
  run: echo "Solo si todo está bien"

# Se ejecuta solo si algo falló
- name: "On failure"
  if: failure()
  run: echo "Solo si algo falló"

# Se ejecuta SIEMPRE (éxito, fallo, cancelación)
- name: "Always run"
  if: always()
  run: echo "Siempre se ejecuta"

# Se ejecuta solo si fue cancelado
- name: "On cancelled"
  if: cancelled()
  run: echo "Solo si fue cancelado"
```

### 2. Comparaciones de strings 📝

```yml
# Comparación exacta
- name: "Main branch only"
  if: github.ref == 'refs/heads/main'
  run: echo "Solo en rama main"

# Contiene texto
- name: "Contains hotfix"
  if: contains(github.ref, 'hotfix')
  run: echo "Solo si la rama contiene 'hotfix'"

# Empieza con
- name: "Feature branches"
  if: startsWith(github.ref, 'refs/heads/feature/')
  run: echo "Solo ramas que empiezan con feature/"

# Termina con
- name: "Release branches"
  if: endsWith(github.ref, '-release')
  run: echo "Solo ramas que terminan con -release"
```

### 3. Operadores lógicos 🧠

```yml
# Comparación exacta
- name: "Main branch only"
  if: github.ref == 'refs/heads/main'
  run: echo "Solo en rama main"

# Contiene texto
- name: "Contains hotfix"
  if: contains(github.ref, 'hotfix')
  run: echo "Solo si la rama contiene 'hotfix'"

# Empieza con
- name: "Feature branches"
  if: startsWith(github.ref, 'refs/heads/feature/')
  run: echo "Solo ramas que empiezan con feature/"

# Termina con
- name: "Release branches"
  if: endsWith(github.ref, '-release')
  run: echo "Solo ramas que terminan con -release"
```

### 4. Funciones de contexto 🌐

```yml
# AND (&&)
- name: "Main and push"
  if: github.ref == 'refs/heads/main' && github.event_name == 'push'
  run: echo "Solo push a main"

# OR (||)
- name: "Main or develop"
  if: github.ref == 'refs/heads/main' || github.ref == 'refs/heads/develop'
  run: echo "Solo main o develop"

# NOT (!)
- name: "Not main"
  if: github.ref != 'refs/heads/main'
  run: echo "Cualquier rama excepto main"

# Combinaciones complejas
- name: "Complex condition"
  if: (github.event_name == 'push') && (github.ref == 'refs/heads/main' || startsWith(github.ref, 'refs/heads/release/'))
  run: echo "Push a main o release branches"
```

### 5. Funciones utilitarias 🔧

```yml
# Convertir a JSON
- name: "Debug context"
  if: github.event_name == 'push'
  run: echo '${{ toJSON(github) }}'

# Hash de string
- name: "Cache key"
  if: success()
  run: echo "Cache: ${{ hashFiles('**/package-lock.json') }}"

# Formato de string
- name: "Formatted output"
  if: always()
  run: echo "${{ format('Build {0} on {1}', github.run_number, github.ref) }}"
```

## 🎯 Ejemplos prácticos comunes

### Cleanup que siempre se ejecuta

```yml
- name: "Cleanup"
  if: always() # ← Como en tu código
  run: |
    rm -f ~/.ssh/id_rsa
    docker system prune -f
```

### Deploy solo en main y si tests pasaron

```yml
- name: "Deploy"
  if: success() && github.ref == 'refs/heads/main'
  run: echo "Desplegando..."
```

### Notificación solo si falló

```yml
- name: "Notify failure"
  if: failure()
  run: |
    curl -X POST "$SLACK_WEBHOOK" \
    -d '{"text":"Build failed!"}'
```

### Diferentes acciones por rama

```yml
- name: "Development deploy"
  if: github.ref == 'refs/heads/develop'
  run: echo "Deploy to staging"

- name: "Production deploy"
  if: github.ref == 'refs/heads/main'
  run: echo "Deploy to production"
```

## 🔄 Matrix Strategy (Estrategia de Matriz)

El parámetro `matrix` te permite ejecutar el mismo job múltiples veces con diferentes configuraciones. Es ideal para:

- Desplegar a múltiples servidores
- Probar en diferentes versiones
- Ejecutar comandos en paralelo

### 📋 Sintaxis Básica

```yaml
strategy:
  matrix:
    variable: [valor1, valor2, valor3]
```

### 💡 Ejemplos con Matrix

#### Ejemplo 1: Deploy a Múltiples Servidores

```yaml
name: Multi-Server Deploy
on: [push]

jobs:
  deploy:
    runs-on: ubuntu-latest
    strategy:
      matrix:
        server:
          - { host: "server1.com", user: "deploy", env: "staging" }
          - { host: "server2.com", user: "admin", env: "production" }
          - { host: "server3.com", user: "ubuntu", env: "development" }

    steps:
      - uses: actions/checkout@v4

      - name: Deploy to ${{ matrix.server.env }}
        uses: ./.github/actions/shh_connect
        with:
          host: ${{ matrix.server.host }}
          user: ${{ matrix.server.user }}
          ssh_private_key: ${{ secrets.SSH_PRIVATE_KEY }}
          command: |
            echo "Deploying to ${{ matrix.server.env }} environment"
            cd /var/www/app
            git pull origin main
            sudo systemctl restart nginx
```

#### Ejemplo 2: Matrix con Variables Simples

```yaml
jobs:
  backup:
    runs-on: ubuntu-latest
    strategy:
      matrix:
        database: [users, products, orders, analytics]
        format: [sql, json]

    steps:
      - name: Backup ${{ matrix.database }} as ${{ matrix.format }}
        run: |
          if [ "${{ matrix.format }}" == "sql" ]; then
            mysqldump ${{ matrix.database }} > backup_${{ matrix.database }}.sql
          else
            mysql -e "SELECT * FROM ${{ matrix.database }}" --json > backup_${{ matrix.database }}.json
          fi
```

#### Ejemplo 3: Matrix con Exclusiones

```yaml
strategy:
  matrix:
    environment: [staging, production]
    region: [us-east, us-west, europe]
    exclude:
      - environment: staging
        region: europe # No staging en Europa

steps:
  - name: Deploy to ${{ matrix.environment }} in ${{ matrix.region }}
    run: kubectl apply -f deployment.yaml
```

#### Ejemplo 4: Matrix con Include (configuraciones adicionales)

```yaml
strategy:
  matrix:
    environment: [staging, production]
    include:
      - environment: staging
        host: "staging.miapp.com"
        user: "test-deploy"
        port: "2222"
      - environment: production
        host: "miapp.com"
        user: "prod-deploy"
        port: "22"
```

### 🎯 Configuraciones Avanzadas de Matrix

#### Fail-fast y Max-parallel

```yaml
strategy:
  fail-fast: false # No detener otros jobs si uno falla
  max-parallel: 2 # Máximo 2 jobs en paralelo
  matrix:
    server: [server1, server2, server3, server4]
```

#### Matrix Dinámico desde JSON

```yaml
jobs:
  setup:
    runs-on: ubuntu-latest
    outputs:
      matrix: ${{ steps.set-matrix.outputs.matrix }}
    steps:
      - id: set-matrix
        run: |
          echo "matrix={\"server\":[\"server1\",\"server2\",\"server3\"]}" >> $GITHUB_OUTPUT

  deploy:
    needs: setup
    strategy:
      matrix: ${{ fromJson(needs.setup.outputs.matrix) }}
    steps:
      - name: Deploy to ${{ matrix.server }}
        run: echo 'Deploy to ${{ matrix.server }}'
```

### 📊 Ventajas del Matrix

| Ventaja                         | Descripción                                       |
| ------------------------------- | ------------------------------------------------- |
| **Paralelización**              | Ejecuta múltiples configuraciones simultáneamente |
| **DRY (Don't Repeat Yourself)** | Un solo workflow para múltiples escenarios        |
| **Escalabilidad**               | Fácil agregar/quitar configuraciones              |
| **Visibilidad**                 | GitHub muestra cada combinación por separado      |

### ⚠️ Consideraciones Importantes

1. **Límites de GitHub**: Máximo 256 jobs por matriz
2. **Tiempo de ejecución**: Cada combinación cuenta hacia el límite de tiempo
3. **Costo**: En cuentas privadas, cada job consume minutos
4. **Dependencias**: Los jobs de matriz se ejecutan independientemente

## 🔍 Tu caso específico

En tu acción SSH, if: always() es perfecto porque:

- 🔐 Seguridad: Las claves SSH deben limpiarse siempre
- 🧹 Limpieza: Evita acumular archivos temporales
- 🛡️ Robustez: Funciona aunque el comando SSH falle

---

## ¡Es una muy buena práctica de seguridad! 🚀
