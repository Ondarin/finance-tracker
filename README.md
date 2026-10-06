Finance Tracker — система управління особистими фінансами

Навчальна практика з програмування, **частина 3** (клієнтська частина). Тема №1.

Застосунок для обліку доходів і витрат, встановлення місячного бюджету, цілі заощаджень та перегляду статистики за категоріями.

## Стек

| Шар | Технології |
|---|---|
| Клієнт | React 18, React Router 6, Vite, SCSS (Dart Sass), Fetch API |
| Архітектура клієнта | компонентна (presentational / container), власний DI-контейнер |
| Браузерні API | localStorage (кеш і офлайн-режим), Notifications (перевищення бюджету) |
| Сервер | Node.js, Express, JSON-файл як сховище, Swagger UI (OpenAPI 3) |

## Структура

```
finance-tracker/
├── client/                 # React-застосунок
│   └── src/
│       ├── components/     # перевикористовувані компоненти (Navbar, StatCard, ...)
│       ├── pages/          # сторінки (Dashboard, Transactions, Budget)
│       ├── hooks/          # container-логіка (useFinance)
│       ├── services/       # HttpClient, TransactionService, BudgetService, ...
│       ├── di/             # DI-контейнер, провайдер, composition root
│       └── styles/         # _variables.scss, _mixins.scss, main.scss, components/*.scss
└── server/                 # REST API (index.js, openapi.json)
```

## Запуск (клієнт + сервер)

Потрібен Node.js 18+.

**1. Сервер**
```bash
cd server
npm install
npm start
```
API: http://localhost:4000/api · Swagger: http://localhost:4000/api-docs

**2. Клієнт** (в іншому терміналі)
```bash
cd client
npm install
npm run dev
```
Застосунок: http://localhost:5173

Якщо API працює на іншій адресі — створіть `client/.env` за зразком `client/.env.example`.

## Збірка
```bash
cd client && npm run build
```

## Функціонал
- CRUD транзакцій (доходи / витрати), фільтрація
- Огляд за місяць: доходи, витрати, заощадження, діаграма за категоріями
- Місячний ліміт та ціль заощаджень, індикатори прогресу
- Сповіщення браузера при перевищенні бюджету
- Офлайн-режим: останні дані беруться з localStorage, якщо сервер недоступний
- Адаптивна верстка (desktop / tablet / mobile)

## Автор
Федько Андрій Володимирович, група КН-31, ТОВ «Фаховий передвищий коледж «ОПТІМА», 2026.
