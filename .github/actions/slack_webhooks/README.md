# Slack Webhook Notification Action 📢

Una acción personalizada de GitHub Actions para enviar notificaciones ricas y profesionales a Slack usando webhooks, sin dependencias externas.

## 📋 Características

- ✅ Implementación nativa sin dependencias externas
- ✅ Mensajes enriquecidos con attachments y colores
- ✅ Información contextual automática del workflow
- ✅ Validación robusta de URLs de webhook
- ✅ Manejo inteligente de estados (success, failure, warning)
- ✅ Enlaces directos al workflow run
- ✅ Cleanup automático de archivos temporales
- ✅ Emojis automáticos según el estado

## 🚀 Uso Básico

```yaml
name: Slack Notifications
on: [push, pull_request]

jobs:
  notify:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Notify Success
        uses: ./.github/actions/slack_webhooks
        with:
          webhook_url: ${{ secrets.SLACK_WEBHOOK }}
          title: "Build Successful"
          message: "The build completed successfully!"
          status: "success"
```

## 📝 Parámetros de Entrada

| Parámetro     | Descripción                 | Requerido | Default                              |
| ------------- | --------------------------- | --------- | ------------------------------------ |
| `webhook_url` | URL del webhook de Slack    | ✅ Sí     | -                                    |
| `message`     | Mensaje a mostrar           | ❌ No     | `"Notification from GitHub Actions"` |
| `title`       | Título del mensaje          | ❌ No     | `"GitHub Actions Notification"`      |
| `channel`     | Canal de Slack (opcional)   | ❌ No     | `"not-gh-act"`                       |
| `username`    | Nombre de usuario a mostrar | ❌ No     | `"GitHub Actions Bot"`               |
| `icon_emoji`  | Emoji como ícono            | ❌ No     | `":rocket:"`                         |
| `color`       | Color del attachment        | ❌ No     | `"good"`                             |
| `status`      | Estado del build            | ❌ No     | `"info"`                             |

### 🎨 Valores de `status` y colores automáticos

| Status    | Color              | Emoji | Uso                 |
| --------- | ------------------ | ----- | ------------------- |
| `success` | Verde (good)       | ✅    | Builds exitosos     |
| `failure` | Rojo (danger)      | ❌    | Builds fallidos     |
| `warning` | Amarillo (warning) | ⚠️    | Advertencias        |
| `info`    | Personalizado      | ℹ️    | Información general |

## 🔐 Configuración del Webhook de Slack

### Paso 1: Crear Incoming Webhook en Slack

1. Ve a [Slack API Apps](https://api.slack.com/apps)
2. Click **Create New App** → **From scratch**
3. Nombre: `GitHub Actions Notifications`
4. Selecciona tu workspace
5. Ve a **Incoming Webhooks** → **Activate Incoming Webhooks**
6. Click **Add New Webhook to Workspace**
7. Selecciona el canal por defecto
8. Copia la URL del webhook

### Paso 2: Agregar el Webhook como Secreto

1. Ve a tu repositorio en GitHub
2. **Settings** → **Secrets and variables** → **Actions**
3. Click **New repository secret**
4. **Name**: `SLACK_WEBHOOK`
5. **Secret**: Pega la URL del webhook
6. Click **Add secret**

## 💡 Ejemplos de Uso

### Ejemplo 1: Notificación de Deploy Exitoso

```yaml
- name: Deploy Success Notification
  uses: ./.github/actions/slack_webhooks
  with:
    webhook_url: ${{ secrets.SLACK_WEBHOOK }}
    title: "🚀 Production Deploy Successful"
    message: |
      Production deployment completed successfully!

      **Changes:**
      - Fixed login bug
      - Updated user dashboard
      - Performance improvements
    status: "success"
    channel: "#deployments"
```

### Ejemplo 2: Notificación de Error

```yaml
- name: Build Failure Notification
  if: failure()
  uses: ./.github/actions/slack_webhooks
  with:
    webhook_url: ${{ secrets.SLACK_WEBHOOK }}
    title: "Build Failed"
    message: "The build process encountered an error. Please check the logs."
    status: "failure"
    channel: "#dev-alerts"
    username: "Build Bot"
    icon_emoji: ":warning:"
```

### Ejemplo 3: Notificación Personalizada

```yaml
- name: Custom Notification
  uses: ./.github/actions/slack_webhooks
  with:
    webhook_url: ${{ secrets.SLACK_WEBHOOK }}
    title: "Security Scan Complete"
    message: "Security vulnerability scan completed. No critical issues found."
    status: "info"
    color: "#0066cc"
    channel: "#security"
    username: "Security Bot"
    icon_emoji: ":shield:"
```

### Ejemplo 4: Notificación con Matrix

```yaml
strategy:
  matrix:
    environment: [staging, production]

steps:
  - name: Notify Deploy to ${{ matrix.environment }}
    uses: ./.github/actions/slack_webhooks
    with:
      webhook_url: ${{ secrets.SLACK_WEBHOOK }}
      title: "Deploy to ${{ matrix.environment }}"
      message: "Deployment to ${{ matrix.environment }} environment completed"
      status: "success"
      channel: "#deployments"
```

## 🛠️ Workflow Completo de Ejemplo

```yaml
name: CI/CD with Slack Notifications
on:
  push:
    branches: [main, develop]
  pull_request:
    branches: [main]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Run Tests
        run: npm test

      - name: Test Success Notification
        if: success()
        uses: ./.github/actions/slack_webhooks
        with:
          webhook_url: ${{ secrets.SLACK_WEBHOOK }}
          title: "Tests Passed ✅"
          message: "All tests are passing on branch ${{ github.ref_name }}"
          status: "success"

      - name: Test Failure Notification
        if: failure()
        uses: ./.github/actions/slack_webhooks
        with:
          webhook_url: ${{ secrets.SLACK_WEBHOOK }}
          title: "Tests Failed ❌"
          message: "Tests are failing on branch ${{ github.ref_name }}. Please check the logs."
          status: "failure"

  deploy:
    needs: test
    runs-on: ubuntu-latest
    if: github.ref == 'refs/heads/main'
    steps:
      - uses: actions/checkout@v4

      - name: Deploy Application
        run: echo "Deploying..."

      - name: Deploy Success Notification
        if: success()
        uses: ./.github/actions/slack_webhooks
        with:
          webhook_url: ${{ secrets.SLACK_WEBHOOK }}
          title: "🚀 Production Deploy Successful"
          message: |
            Production deployment completed!

            **Commit:** ${{ github.event.head_commit.message }}
            **Author:** ${{ github.event.head_commit.author.name }}
          status: "success"
          channel: "#deployments"

      - name: Deploy Failure Notification
        if: failure()
        uses: ./.github/actions/slack_webhooks
        with:
          webhook_url: ${{ secrets.SLACK_WEBHOOK }}
          title: "🚨 Production Deploy Failed"
          message: "Production deployment failed! Immediate attention required."
          status: "failure"
          channel: "#critical-alerts"
```

## 📊 Información Automática Incluida

Cada mensaje incluye automáticamente:

| Campo          | Descripción            | Ejemplo                            |
| -------------- | ---------------------- | ---------------------------------- |
| **Repository** | Nombre del repositorio | `owner/repo-name`                  |
| **Branch**     | Rama actual            | `main`, `develop`, `feature/login` |
| **Event**      | Tipo de evento         | `push`, `pull_request`             |
| **Actor**      | Usuario que ejecutó    | `@username`                        |
| **Workflow**   | Nombre del workflow    | `CI/CD Pipeline`                   |
| **Run ID**     | Enlace al workflow     | `#123` (clickeable)                |

## 🎨 Personalización Avanzada

### Colores Personalizados

```yaml
# Colores predefinidos
color: "good"      # Verde
color: "warning"   # Amarillo
color: "danger"    # Rojo

# Colores hexadecimales
color: "#FF5733"   # Naranja personalizado
color: "#36a64f"   # Verde personalizado
color: "#764FA5"   # Morado personalizado
```

### Emojis Personalizados

```yaml
icon_emoji: ":rocket:"     # Cohete
icon_emoji: ":white_check_mark:"  # Check verde
icon_emoji: ":x:"          # X roja
icon_emoji: ":warning:"    # Advertencia
icon_emoji: ":information_source:"  # Información
```

## 🐛 Troubleshooting

### Error: "Invalid Slack webhook URL format"

- ✅ Verifica que la URL empiece con `https://hooks.slack.com/services/`
- ✅ Copia la URL completa desde Slack
- ✅ No incluyas espacios o caracteres extra

### Error: "HTTP Status Code: 404"

- ✅ El webhook fue eliminado o deshabilitado
- ✅ Regenera el webhook en Slack
- ✅ Actualiza el secreto en GitHub

### Error: "jq: command not found"

- ✅ La acción instala `jq` automáticamente en runners estándar
- ✅ En runners self-hosted, instala: `sudo apt-get install jq`

### El mensaje no aparece en el canal especificado

- ✅ Verifica que el canal existe
- ✅ El bot debe tener permisos para escribir en el canal
- ✅ Usa formato `#canal` o `@usuario` para DM

## ⚠️ Consideraciones de Seguridad

1. **Nunca** hardcodees la URL del webhook en el código
2. Usa **secretos** para almacenar la URL del webhook
3. Considera usar webhooks específicos para diferentes ambientes
4. Revisa periódicamente los webhooks activos en Slack
5. La acción limpia automáticamente archivos temporales

## 📞 Soporte

Si encuentras problemas:

1. Verifica que el webhook de Slack sea válido
2. Revisa los logs del workflow en GitHub
3. Confirma que el secreto `SLACK_WEBHOOK` esté configurado
4. Prueba el webhook manualmente con `curl`

## 🔗 Links Útiles

- [Slack Incoming Webhooks](https://api.slack.com/messaging/webhooks)
- [Slack Message Formatting](https://api.slack.com/reference/surfaces/formatting)
- [GitHub Actions Contexts](https://docs.github.com/en/actions/learn-github-actions/contexts)

---

**Desarrollado con ❤️ por DcDev**
