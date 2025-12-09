# Fintuity E2E Tests Runner

GitHub Actions orchestrator для запуска E2E тестов Fintuity Portal.

## 🚀 Запуск тестов

1. Перейди в [Actions](../../actions/workflows/run-e2e-tests.yml)
2. Нажми **"Run workflow"**
3. Выбери параметры:
   - **Environment**: `dev`, `staging`, `preprod`
   - **Browser**: `chrome`, `firefox`, `edge`
   - **Spec** (опционально): путь к конкретному тесту или оставь пустым
4. Нажми **"Run workflow"**

### Примеры

**Запустить все тесты на DEV:**
- Environment: `dev`
- Browser: `chrome`
- Spec: (пусто)

**Запустить только регистрацию на STAGING:**
- Environment: `staging`
- Browser: `firefox`
- Spec: `portal-e2e/src/integration/registration/*.cy.ts`

## 📊 Результаты

После выполнения доступны артефакты:
- 📸 **Screenshots** - при падении тестов
- 🎥 **Videos** - при падении тестов
- 📝 **Memory logs** - всегда

## 🔐 Секреты (GitHub Secrets)

Settings → Secrets and variables → Actions:

| Секрет | Описание |
|--------|----------|
| `BITBUCKET_USERNAME` | Bitbucket username |
| `BITBUCKET_API_TOKEN` | Bitbucket API token (read-only) |
| `DEV_URL` | https://app.dev.fintuity.com/portal |
| `GMAIL_USER` | Email для тестов |
| `GMAIL_PASSWORD` | Gmail app password |

## 🏗️ Архитектура