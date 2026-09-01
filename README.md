# PolyApiIDE

HTTP-клиент и API IDE во вкладке Chrome: REST, GraphQL, WebSocket, SOAP и gRPC. Коллекции, окружения и ответы хранятся на устройстве. На **Free** аккаунт не нужен.

Это официальная страница продукта. **Исходного кода здесь нет.**

[Установить из Chrome Web Store](https://chromewebstore.google.com/detail/polyapiide/jladdfejldmbglilemedogoeceohbbmb?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) · [Сайт](https://polyapiclient.ru?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) · [Быстрый старт](https://polyapiclient.ru/quick-start?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) · [Возможности](https://polyapiclient.ru/features?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client)

Подойдут Chrome, Microsoft Edge и другие браузеры на Chromium.

---

## Установка

1. Откройте [карточку в Chrome Web Store](https://chromewebstore.google.com/detail/polyapiide/jladdfejldmbglilemedogoeceohbbmb?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client).
2. Нажмите **Добавить в Chrome**.
3. Откройте клиент с иконки на панели, создайте запрос или импортируйте коллекцию, нажмите **Send**.

Ключ и демо — только на [сайте](https://polyapiclient.ru?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client#buy), не через магазин. В IDE: **Настройки → Лицензия**.

---

## Скриншоты

![Рабочее место на Free](https://polyapiclient.ru/demo/shots/overview-free.png)

![Платные разделы в том же окне](https://polyapiclient.ru/demo/shots/overview-lifetime.png)

---

## Что умеет

- Запросы REST, GraphQL, WebSocket, SOAP; **gRPC — через JSON-шлюз**, не нативный protobuf
- Несколько пространств, коллекции, окружения, переменные `{{baseUrl}}` и `{{token}}`
- Слои HTTP-настроек: IDE → пространство → запрос
- Скрипты до и после отправки в локальной песочнице (`poly`; `pm` — совместимый алиас)
- Импорт на Free: OpenAPI, WSDL, GraphQL, `.proto`, AsyncAPI, Postman, curl, Insomnia, Hoppscotch, Thunder
- Проверки после Send, прогоны коллекций и нагрузка из браузера
- Интерфейс на русском и английском, светлая и тёмная тема

На сервер уходит только то, что вы сами включили: ключ, ручной бэкап, история помощника, обращение в поддержку.

---

## Тарифы

Цены и оплата — на [сайте](https://polyapiclient.ru?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client#buy). Суммы сюда не копируем. Месяц и Год — один платный набор; Год на 12 месяцев со скидкой.

| | Free | Месяц / Год | Lifetime | Демо 14 дней |
|---|---|---|---|---|
| Клиент, импорт, скрипты | Да | Да | Да | Да |
| Аккаунт | Не нужен | Email для ключа | Email и архив | Форма на сайте |
| QA после Send | Да | Да | Да | Да |
| Сценарии QA, прокси, AI, патчи | Нет | Да | Да | Да |
| Прогоны коллекции / папки / нагрузки | 3 / 3 / 1 в месяц | Без лимита | Без лимита | Без лимита |
| Активные сессии | 2 | 5 | 5 | 1 |
| Новая сборка | После публикации в магазине | После публикации в магазине | Сразу в архиве | Как Free; zip нет |

**Lifetime** — разовая оплата, не подписка. Исправления текущей линейки бесплатны; крупные (major) обновления — по желанию, не «все будущие версии». Ключ и установочный архив храните у себя.

**Демо** — 14 дней полного набора, один раз на email, только с сайта. Zip не выдаётся. Перед окончанием сделайте бэкап.

Подробности: [возможности](https://polyapiclient.ru/features?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client).

---

## Чего нет

- Общего облачного workspace, как у Postman
- Коллекций файлами в Git, как у Bruno
- CLI для пайплайна (Newman, `bru`)
- Нативной нагрузки уровня k6 / JMeter — прогоны идут из браузера
- Нативного gRPC: только JSON-шлюз

Нужны файлы в Git — смотрите Bruno. Нужны облако команды и мониторы — Postman. Нужен клиент **в Chrome**, без обязательного аккаунта и с оплатой с сайта — PolyApiIDE.

---

## Ссылки

| | |
|---|---|
| Установка | [Chrome Web Store](https://chromewebstore.google.com/detail/polyapiide/jladdfejldmbglilemedogoeceohbbmb?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) |
| Сайт | [polyapiclient.ru](https://polyapiclient.ru?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) |
| Быстрый старт | [polyapiclient.ru/quick-start](https://polyapiclient.ru/quick-start?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) |
| Возможности | [polyapiclient.ru/features](https://polyapiclient.ru/features?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) |
| Сравнение с Postman | [polyapiclient.ru/compare](https://polyapiclient.ru/compare?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) |
| Вопросы и ответы | [polyapiclient.ru/faq](https://polyapiclient.ru/faq?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) |
| Конфиденциальность | [polyapiclient.ru/privacy](https://polyapiclient.ru/privacy?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) |
| Соглашение | [polyapiclient.ru/terms](https://polyapiclient.ru/terms?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) |
| Поддержка | [polyapiclient.ru/support](https://polyapiclient.ru/support?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) · support@polyapiide.ru |

Баг или пожелание — в Issues этого репозитория, если они включены. Оплата и ключи — только через сайт.

---

## English

PolyApiIDE is an HTTP client and API IDE in a Chrome tab. Collections stay on the device. **Free needs no account.** This repository is the official product page and **does not contain source code**.

[Install](https://chromewebstore.google.com/detail/polyapiide/jladdfejldmbglilemedogoeceohbbmb?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) · [Website](https://polyapiclient.ru/en?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) · [Quick start](https://polyapiclient.ru/en/quick-start?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) · [Features](https://polyapiclient.ru/en/features?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client)

Works in Chrome, Edge, and other Chromium browsers. Buy and demo only on the website, not through the Chrome Web Store.

**Free** — send, import, scripts, QA after Send; monthly run limits. **Month / Year** — QA scenarios, unlimited runs, proxy, AI, patches, up to 5 sessions. **Lifetime** — one-time key plus install archive; line fixes are free; major updates are optional, not “every future version”. **Demo** — 14 days of the paid set, once per email, website form only.

Not included: shared cloud workspace, Git-on-disk collections, CLI/CI runner, native gRPC, k6-class load.

Pick **Bruno** for collections as Git files. Pick **Postman** for team cloud and monitors. Pick **PolyApiIDE** for a Chrome tab, local-first Free, and checkout on the website.
