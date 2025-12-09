# Fintuity E2E Tests Runner

Автоматизированные E2E тесты для Fintuity Portal, запускаемые через GitHub Actions.

## 🚀 Запуск тестов

### Через GitHub Actions (рекомендуется)

1. Перейди в [Actions](../../actions/workflows/run-e2e-tests.yml)
2. Нажми "Run workflow"
3. Выбери параметры:
    - **Environment**: `dev`, `staging`, `preprod`
    - **Browser**: `chrome`, `firefox`, `edge`
4. Нажми "Run workflow"

### Локально (для разработки)
```bash
# Установка зависимостей
npm ci

# Открыть Cypress UI для выбора тестов
npm run cypress:open

# Запустить все тесты на DEV
npm run e2e:portal:dev

# Запустить все тесты на STAGING
npm run e2e:portal:staging

# Запустить все тесты локально (localhost:6200)
npm run e2e:portal:local
```

## 📁 Структура проекта
```
e2e-tests/
├── portal-e2e/
│   ├── src/
│   │   ├── fixtures/       # Тестовые данные
│   │   ├── integration/    # Тесты
│   │   └── support/        # Хелперы и команды
│   └── cypress.json        # Конфигурация Cypress
├── .github/
│   └── workflows/
│       └── run-e2e-tests.yml  # GitHub Actions workflow
└── package.json
```

## 🔐 Секреты (GitHub Secrets)

Необходимые секреты в Settings → Secrets and variables → Actions:

- `BITBUCKET_USERNAME` - Bitbucket username
- `BITBUCKET_API_TOKEN` - Bitbucket API token
- `DEV_URL` - https://app.dev.fintuity.com/portal
- `GMAIL_USER` - Email для тестов
- `GMAIL_PASSWORD` - Gmail app password

## 📊 Результаты тестов

После выполнения тестов доступны артефакты:
- 📸 Скриншоты (при падении тестов)
- 🎥 Видео (при падении тестов)
- 📝 Логи памяти (всегда)

## 🛠️ Технологии

- **Cypress 9.7.0** - E2E тестирование
- **Node.js 20.18.1** - Runtime
- **GitHub Actions** - CI/CD (16GB RAM, 4 CPU cores)
- **Bitbucket** - Хранение кода

## 📝 Локальная настройка Gmail

Для локальной разработки создай файл `shared/gmail-creds.local.js`:
```javascript
module.exports = {
  BASE_EMAIL: 'your-email@gmail.com',
  GMAIL_PASSWORD: 'your-app-password',
};
```

⚠️ Этот файл не коммитится в Git (добавлен в `.gitignore`)