# SSH Connect Action 🔐

Una acción personalizada de GitHub Actions para conectarse a servidores remotos vía SSH y ejecutar comandos de forma segura.

## 📋 Características

- ✅ Conexión SSH segura con validación de claves
- ✅ Test automático de conexión antes de ejecutar comandos
- ✅ Soporte para puertos personalizados
- ✅ Limpieza automática de claves SSH (seguridad)
- ✅ Manejo robusto de errores
- ✅ Logs informativos con emojis

## 🚀 Uso Básico

```yaml
name: Deploy to Server
on: [push]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Deploy via SSH
        uses: ./.github/actions/shh_connect
        with:
          host: "mi-servidor.com"
          user: "ubuntu"
          ssh_private_key: ${{ secrets.SSH_PRIVATE_KEY }}
          command: "sudo systemctl restart nginx"
```

## 📝 Parámetros de Entrada

| Parámetro         | Descripción                | Requerido | Default  |
| ----------------- | -------------------------- | --------- | -------- |
| `host`            | Dirección del servidor SSH | ✅ Sí     | -        |
| `user`            | Usuario SSH                | ✅ Sí     | -        |
| `ssh_private_key` | Clave privada SSH          | ✅ Sí     | -        |
| `command`         | Comando a ejecutar         | ✅ Sí     | `ls -la` |
| `port`            | Puerto SSH                 | ❌ No     | `22`     |

## 🔐 Configuración de Secretos

### Paso 1: Generar clave SSH (si no la tienes)

```bash
# En tu máquina local
ssh-keygen -t rsa -b 4096 -C "github-actions@mi-proyecto.com"
```

### Paso 2: Copiar clave pública al servidor

```bash
# Copiar la clave pública al servidor
ssh-copy-id -i ~/.ssh/id_rsa.pub usuario@mi-servidor.com
```

### Paso 3: Agregar clave privada a GitHub Secrets

1. Ve a tu repositorio en GitHub
2. **Settings** → **Secrets and variables** → **Actions**
3. Click **New repository secret**
4. **Name**: `SSH_PRIVATE_KEY`
5. **Secret**: Copia el contenido de tu clave privada:
   ```bash
   cat ~/.ssh/id_rsa
   ```
6. Click **Add secret**

## 💡 Ejemplos de Uso

### Ejemplo 1: Deploy Simple

```yaml
- name: Deploy Application
  uses: ./.github/actions/shh_connect
  with:
    host: "production-server.com"
    user: "deploy"
    ssh_private_key: ${{ secrets.SSH_PRIVATE_KEY }}
    command: |
      cd /var/www/html
      git pull origin main
      npm install
      npm run build
      sudo systemctl restart nginx
```

### Ejemplo 2: Puerto Personalizado

```yaml
- name: Connect to Custom Port
  uses: ./.github/actions/shh_connect
  with:
    host: "mi-servidor.com"
    user: "admin"
    ssh_private_key: ${{ secrets.SSH_PRIVATE_KEY }}
    command: "docker ps"
    port: "2222"
```

### Ejemplo 3: Backup de Base de Datos

```yaml
- name: Database Backup
  uses: ./.github/actions/shh_connect
  with:
    host: "db-server.com"
    user: "backup-user"
    ssh_private_key: ${{ secrets.SSH_PRIVATE_KEY }}
    command: |
      mysqldump -u root -p${{ secrets.DB_PASSWORD }} mydb > backup_$(date +%Y%m%d).sql
      aws s3 cp backup_$(date +%Y%m%d).sql s3://my-backups/
```

### Ejemplo 4: Comandos Múltiples

```yaml
- name: Multiple Commands
  uses: ./.github/actions/shh_connect
  with:
    host: "app-server.com"
    user: "deployer"
    ssh_private_key: ${{ secrets.SSH_PRIVATE_KEY }}
    command: |
      echo "Starting deployment..."
      cd /opt/myapp
      docker-compose down
      docker-compose pull
      docker-compose up -d
      echo "Deployment completed!"
```

## 🛠️ Workflow Completo de Ejemplo

```yaml
name: CI/CD Pipeline
on:
  push:
    branches: [main]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Run Tests
        run: npm test

  deploy:
    needs: test
    runs-on: ubuntu-latest
    if: github.ref == 'refs/heads/main'
    steps:
      - uses: actions/checkout@v4

      - name: Deploy to Staging
        uses: ./.github/actions/shh_connect
        with:
          host: ${{ vars.STAGING_HOST }}
          user: ${{ vars.STAGING_USER }}
          ssh_private_key: ${{ secrets.SSH_PRIVATE_KEY }}
          command: |
            cd /var/www/staging
            git pull origin main
            npm install --production
            pm2 restart app

      - name: Deploy to Production
        uses: ./.github/actions/shh_connect
        with:
          host: ${{ vars.PRODUCTION_HOST }}
          user: ${{ vars.PRODUCTION_USER }}
          ssh_private_key: ${{ secrets.SSH_PRIVATE_KEY }}
          command: |
            cd /var/www/production
            git pull origin main
            npm install --production
            pm2 restart app
```

## 🔧 Variables de Repositorio Recomendadas

Crea estas variables en **Settings** → **Secrets and variables** → **Actions** → **Variables**:

| Variable          | Ejemplo             | Descripción            |
| ----------------- | ------------------- | ---------------------- |
| `STAGING_HOST`    | `staging.miapp.com` | Servidor de staging    |
| `STAGING_USER`    | `ubuntu`            | Usuario de staging     |
| `PRODUCTION_HOST` | `miapp.com`         | Servidor de producción |
| `PRODUCTION_USER` | `deploy`            | Usuario de producción  |

## ⚠️ Consideraciones de Seguridad

1. **Nunca** hardcodees credenciales en el código
2. Usa **secretos** para claves privadas
3. Usa **variables** para información no sensible
4. La acción limpia automáticamente las claves SSH después de usarlas
5. Considera usar claves SSH específicas para CI/CD (no tus claves personales)

## 🐛 Troubleshooting

### Error: "SSH connection test failed"

- ✅ Verifica que el host sea accesible
- ✅ Confirma que el usuario existe en el servidor
- ✅ Asegúrate que la clave privada sea correcta
- ✅ Verifica el puerto SSH (default: 22)

### Error: "SSH client not found"

- ✅ La acción instala automáticamente openssh-client
- ✅ Asegúrate de usar `ubuntu-latest` como runner

### Error: "Command execution failed"

- ✅ Prueba el comando manualmente en el servidor
- ✅ Verifica permisos del usuario
- ✅ Revisa la sintaxis del comando

## 📞 Soporte

Si encuentras problemas:

1. Revisa los logs del workflow
2. Verifica la configuración de secretos
3. Prueba la conexión SSH manualmente
4. Abre un issue en el repositorio

---

## 🔄 Matrix Strategy (Estrategia de Matriz)

El parámetro `matrix` te permite ejecutar el mismo job múltiples veces con diferentes configuraciones. Es ideal para:

- Desplegar a múltiples servidores- Probar en diferentes versiones- Ejecutar comandos en paralelo

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
        uses: ./.github/actions/shh_connect
        with:
          host: "db-server.com"
          user: "backup"
          ssh_private_key: ${{ secrets.SSH_PRIVATE_KEY }}
          command: |
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
    uses: ./.github/actions/shh_connect
    with:
      host: ${{ matrix.environment }}-${{ matrix.region }}.miapp.com
      user: "deploy"
      ssh_private_key: ${{ secrets.SSH_PRIVATE_KEY }}
      command: "kubectl apply -f deployment.yaml"
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

steps:
  - name: Deploy to ${{ matrix.environment }}
    uses: ./.github/actions/shh_connect
    with:
      host: ${{ matrix.host }}
      user: ${{ matrix.user }}
      ssh_private_key: ${{ secrets.SSH_PRIVATE_KEY }}
      command: "echo 'Deploying to ${{ matrix.environment }}'"
      port: ${{ matrix.port }}
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
      - uses: ./.github/actions/shh_connect
        with:
          host: ${{ matrix.server }}.com
          user: "deploy"
          ssh_private_key: ${{ secrets.SSH_PRIVATE_KEY }}
          command: "echo 'Deploy to ${{ matrix.server }}'"
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

---

**Desarrollado con ❤️ por DcDev**
