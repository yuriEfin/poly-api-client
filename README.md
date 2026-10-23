# PolyApiIDE

HTTP-клиент и API IDE во вкладке Chrome или Firefox: REST, GraphQL, WebSocket, SOAP и gRPC. Коллекции, окружения и ответы хранятся на устройстве. На **Free** аккаунт не нужен.

Это официальная страница продукта. **Исходного кода здесь нет.**

[Chrome Web Store](https://chromewebstore.google.com/detail/polyapiide/jladdfejldmbglilemedogoeceohbbmb?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) · [Firefox Add-ons](https://addons.mozilla.org/ru/firefox/addon/http-api-client-polyapiide/) · [Сайт](https://polyapiclient.ru?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) · [Быстрый старт](https://polyapiclient.ru/quick-start?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) · [Возможности](https://polyapiclient.ru/features?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client)

Подойдут Chrome, Microsoft Edge и другие браузеры на Chromium, а также Firefox.

---

## Установка

**Chrome, Edge и другие Chromium-браузеры**

1. Откройте [карточку в Chrome Web Store](https://chromewebstore.google.com/detail/polyapiide/jladdfejldmbglilemedogoeceohbbmb?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client).
2. Нажмите **Добавить в Chrome**.
3. Откройте клиент с иконки на панели, создайте запрос или импортируйте коллекцию, нажмите **Send**.

**Firefox**

1. Откройте [карточку в Firefox Add-ons (AMO)](https://addons.mozilla.org/ru/firefox/addon/http-api-client-polyapiide/).
2. Нажмите **Добавить в Firefox**.
3. Дальше — так же, как в Chrome.

Сборка для Firefox функционально та же, кроме одного пункта: **Мониторинг по расписанию работает только в Chrome** (нужен `chrome.offscreen`, которого нет в WebExtensions API Firefox).

Ключ и демо — только на [сайте](https://polyapiclient.ru?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client#buy), не через магазин. В IDE: **Настройки → Лицензия**.

---

## Скриншоты

![Рабочее место на Free](https://polyapiclient.ru/demo/shots/overview-free.png)

![Платные разделы в том же окне](https://polyapiclient.ru/demo/shots/overview-lifetime.png)

---

## Что умеет

**Запрос и ответ**
- REST, GraphQL, WebSocket, SOAP, **SSE**; **gRPC — через JSON-шлюз**, не нативный protobuf
- URL, метод, Params, Headers, Body (raw, urlencoded, form-data, файл до 5 МБ); GET/HEAD без тела
- Decoded URL и curl-превью после подстановки переменных
- Ответ — дерево JSON, заголовки, консоль сессии, полноэкранный просмотр; тело не обрезается тихо
- Слои HTTP-настроек: IDE → пространство → запрос (включённый слой запроса побеждает)

**Пространства, переменные, окружения**
- Несколько изолированных пространств, каждое — своя вкладка
- Иерархия переменных: запрос → коллекция → пространство → активное окружение; пустое значение сверху не затирает нижнее
- Плейсхолдеры `{{baseUrl}}`, `{{token}}`; динамика `{{guid}}`, `{{uuid}}`, `{{timestamp}}`, `{{isoTimestamp}}`, `{{$randomInt}}`
- Импорт переменных из файла `.env` или JSON прямо в окружение: новые добавляются, совпадающие по имени обновляются

**Авторизация и скрипты**
- Bearer, Basic, API key, OAuth2, JWT — наследуются от папки и коллекции
- Pre-request и after-response скрипты в локальной песочнице; объект `poly`, `pm` — совместимый алиас для готовых коллекций
- Скрипты доступны без ключа

**Импорт (на Free)**
- OpenAPI, WSDL, GraphQL-схемы, `.proto`, AsyncAPI, HAR (DevTools → Save all as HAR), Postman, curl-команды, Insomnia, Hoppscotch, Thunder Client

**Проверки и нагрузка**
- QA после Send: статус, время ответа, тело, JSON path — доступно без ключа
- Free: до 3 прогонов коллекции, 3 папки и 1 нагрузочного прогона в календарный месяц
- Платные тарифы: без квот, QA-сценарии пространства, негативные кейсы, «Завести баг», Collection Runner (Functional — итерации, data file CSV/JSON, stop on error; Performance — Fixed/Ramp up/Spike/Peak), вкладка Load с VU/RPS/p95 и экспортом метрик, PDF-отчёты

**Обмен, захват, автоматизация**
- Live Capture: запросы одной открытой вкладки, только по вашей кнопке — фонового перехвата всего браузера нет
- Патч коллекции, раздела или запроса и экспорт папкой (по файлу на запрос) — платные тарифы; это не git-diff и не git-клиент
- Публичная ссылка на коллекцию (платные тарифы): страница только для чтения, до суток, не больше 10 ссылок в день; экспорт предупреждает, если значения похожи на секреты
- MCP v2: внешний ИИ-инструмент по вашему `client_id` ставит расширению команду в очередь и забирает результат позже — без client_secret и без отдельного MCP-сервера как процесса (платные тарифы)
- AI-ассистент: Ask/Explain к запросу и нагрузке, чат, проектирование коллекции — на ваших ключах моделей, не наших

**Live Rules** *(платные тарифы)*
- Локальные правила блокировки, редиректа или подмены заголовка/тела сетевого запроса — по условию, которое задаёте сами

**Mock-серверы** *(платные тарифы)*
- Правило подставляет своё тело и content-type ответа для запросов, совпадающих по методу и шаблону URL — для IDE, пространства или коллекции

**Мониторинг по расписанию**
- Сохранённый запрос, коллекция или сценарий проверяются по таймеру; алерт — в мессенджер, Pushgateway или ваш webhook
- Free — одна проверка, платные тарифы — до десяти
- Только в Chrome: проверки идут внутри открытого браузера

**Бэкап и команда**
- Снапшот локально, вручную на сервер или на email; облачная история — Free до 3 версий, платные тарифы до 10
- Интеграции с таск-трекерами и мессенджерами из IDE («отправить баг»)

**Интерфейс**
- Русский и английский, светлая и тёмная тема

На сервер уходит только то, что вы сами включили: ключ, ручной бэкап, история помощника, обращение в поддержку.

---

## Тарифы

Цены и оплата — на [сайте](https://polyapiclient.ru?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client#buy). Суммы сюда не копируем.

| | Free | Месяц / Год | Демо 14 дней |
|---|---|---|---|
| Клиент, импорт, скрипты | Да | Да | Да |
| Аккаунт | Не нужен | Email для ключа | Форма на сайте |
| QA после Send | Да | Да | Да |
| Сценарии QA, прокси, AI, патчи, папка, ссылка, MCP | Нет | Да | Да |
| Прогоны коллекции / папки / нагрузки | 3 / 3 / 1 в месяц | Без лимита | Без лимита |
| Активные сессии | 2 | 5 | 1 |
| Новая сборка | После публикации в магазине | После публикации в магазине | Как Free; zip нет |

Месяц и Год — один и тот же платный набор; Год на 12 месяцев со скидкой при оплате сразу за год.

**Про тариф Lifetime.** Как разовая покупка сейчас **не продаётся новым покупателям** — ни на сайте, ни здесь его нет в таблице выше. Тариф не исчез: у тех, кто уже купил Lifetime, ключ работает как раньше — исправления текущей линейки бесплатны, крупные (major) обновления по желанию, новая сборка сразу доступна в архиве без ожидания магазина. Мы наблюдаем за спросом на разовую покупку без подписки и можем вернуть тариф для новых покупателей — конкретной даты возврата нет. Особый случай — пишите в поддержку, обсудим индивидуально.

**Демо** — 14 дней полного набора, один раз на email, только с сайта. Zip не выдаётся. Перед окончанием сделайте бэкап.

Подробности: [возможности](https://polyapiclient.ru/features?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client).

---

## Чего нет

- Общего облачного workspace, как у Postman
- Встроенного Git-клиента и CLI для CI (Newman, `bru`). Папку коллекции можно экспортировать и положить в репозиторий самим
- Собственного MCP-сервера (отдельного процесса): патчи коллекции и job-очередь команд MCP v2 — через обычный REST на нашем сервере
- Нативной нагрузки уровня k6 / JMeter — прогоны идут из браузера
- Нативного gRPC: только JSON-шлюз
- Мониторинга по расписанию в Firefox-сборке (только Chrome и другие Chromium-браузеры)

Нужен Git как основной способ хранить коллекции — смотрите Bruno. Нужны облако команды и мониторы — Postman. Нужен клиент **в браузере**, без обязательного аккаунта и с оплатой с сайта — PolyApiIDE.

---

## Ссылки

| |                                                                                                                                                                     |
|---|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Chrome Web Store | [Установить](https://chromewebstore.google.com/detail/polyapiide/jladdfejldmbglilemedogoeceohbbmb?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) |
| Firefox Add-ons (AMO) | [Установить](https://addons.mozilla.org/ru/firefox/addon/http-api-client-polyapiide/)                                                                               |
| Сайт | [polyapiclient.ru](https://polyapiclient.ru?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client)                                                       |
| Быстрый старт | [polyapiclient.ru/quick-start](https://polyapiclient.ru/quick-start?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client)                               |
| Возможности | [polyapiclient.ru/features](https://polyapiclient.ru/features?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client)                                     |
| Сравнение с Postman | [polyapiclient.ru/compare](https://polyapiclient.ru/compare?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client)                                       |
| Вопросы и ответы | [polyapiclient.ru/faq](https://polyapiclient.ru/faq?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client)                                               |
| Конфиденциальность | [polyapiclient.ru/privacy](https://polyapiclient.ru/privacy?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client)                                       |
| Соглашение | [polyapiclient.ru/terms](https://polyapiclient.ru/terms?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client)                                           |
| Поддержка | [polyapiclient.ru/support](https://polyapiclient.ru/support?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) · support@polyapiide.ru               |

Баг или пожелание — в Issues этого репозитория, если они включены. Оплата и ключи — только через сайт.

---

## English

PolyApiIDE is an HTTP client and API IDE in a Chrome or Firefox tab. Collections stay on the device. **Free needs no account.** This repository is the official product page and **does not contain source code**.

[Chrome Web Store](https://chromewebstore.google.com/detail/polyapiide/jladdfejldmbglilemedogoeceohbbmb?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) · [Firefox Add-ons](https://addons.mozilla.org/en-US/firefox/addon/http-api-clent-polyapiide/) · [Website](https://polyapiclient.ru/en?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) · [Quick start](https://polyapiclient.ru/en/quick-start?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) · [Features](https://polyapiclient.ru/en/features?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client)

Works in Chrome, Edge, other Chromium browsers, and Firefox. Buy and demo only on the website, not through either store.

### What it does

- **Requests** — REST, GraphQL, WebSocket, SOAP, SSE; gRPC through a JSON gateway (not native protobuf). URL, method, Params, Headers, Body (raw/urlencoded/form-data/file up to 5 MB). Decoded URL and curl preview. JSON tree response, headers, session console, fullscreen view, no silent truncation. Settings layered IDE → space → request.
- **Spaces, variables, environments** — several isolated spaces; variable priority request → collection → space → active environment, with empty values not overwriting lower layers; built-ins (`{{guid}}`, `{{uuid}}`, `{{timestamp}}`, `{{isoTimestamp}}`, `{{$randomInt}}`); variables can be imported straight from a `.env` or JSON file into an environment.
- **Auth and scripts** — Bearer, Basic, API key, OAuth2, JWT inherited from folder/collection; pre-request and after-response scripts in a local sandbox (`poly`, with a `pm`-compatible alias); scripts work without a license.
- **Import (Free)** — OpenAPI, WSDL, GraphQL schemas, `.proto`, AsyncAPI, HAR (DevTools → Save all as HAR), Postman, curl, Insomnia, Hoppscotch, Thunder Client.
- **Checks and load** — QA after Send works without a key; Free allows up to 3 collection runs, 3 folder runs and 1 load run per month. Paid plans remove the quota and add workspace QA scenarios, negative cases, "File a bug", the Collection Runner (Functional: iterations, CSV/JSON data file, stop on error; Performance: Fixed/Ramp up/Spike/Peak), a Load tab with VU/RPS/p95 and metrics export, and PDF reports.
- **Share, capture, automation** — Live Capture records one open tab's requests only after you click, not a background sniffer. Paid plans add collection/folder/request patches and folder export (not a git diff or git client), a public read-only collection link (up to 1 day, max 10/day, with a secret-value warning on export), and MCP v2 — an external AI tool can queue a command for the extension using just your `client_id` and fetch the result later, no `client_secret`, no separate MCP server process. An AI assistant (your own model keys) can Ask/Explain and help design a collection.
- **Live Rules** *(paid)* — local rules to block, redirect, or rewrite a network request's header or body, by a condition you set.
- **Mock servers** *(paid)* — a rule serves its own response body and content-type for requests matching a method and URL pattern, scoped to the IDE, a space, or a collection.
- **Scheduled monitoring** — a saved request, collection or scenario is re-checked on a timer with an alert to a messenger, Pushgateway, or your own webhook; Free includes one check, paid plans up to ten. **Chrome only** — the Firefox build drops this feature (no `chrome.offscreen` in the Firefox WebExtensions API).
- **Backup and teams** — manual snapshot to server or email; cloud history keeps the last 3 versions on Free, 10 on paid plans; issue-tracker and messenger integrations from the IDE.
- **Interface** — Russian and English, light and dark theme.

### Plans

**Free** — send, import (including HAR), scripts, SSE, QA after Send; monthly run limits; no account needed. **Month / Year** — the same full set: QA scenarios, unlimited runs, proxy, AI assistant, collection patches, folder export, public collection link, MCP v2 commands from AI tools, Live Rules, Mock servers, up to 5 sessions. Year is the same plan billed for 12 months at a discount. **Demo** — 14 days of the paid set, once per email, website form only, no zip.

**Lifetime** is not sold to new buyers right now — you won't find it in the plans above, on the website, or here. It still exists: anyone who already bought it keeps working under the same terms as before — free fixes within the current line, optional major upgrades, new builds available immediately in the archive without waiting for store publication. We're watching demand for a one-time, no-subscription option and may reopen it for new buyers — there is no promised date. Special case? Email support and we'll discuss it.

Not included: shared cloud workspace, a Git client or CLI/CI runner, a separate MCP server process (patches and MCP v2 commands are plain REST on our server), native gRPC, k6-class load, scheduled monitoring on Firefox.

Pick **Bruno** if collections must live in Git as the primary workflow. Pick **Postman** for team cloud and monitors. Pick **PolyApiIDE** for a browser tab, local-first Free, and checkout on the website.
