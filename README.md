# PolyApiIDE

**Официальная страница PolyApiIDE**  - Api клиент (REST | SOAP | gRPC | GraphQL | WebSocket). В планах GIT и плотная интеграция с ИИ.
Исходного кода расширения здесь нет — только описание и ссылка на установку.

**PolyApiIDE** — расширение для [Google Chrome](https://chromewebstore.google.com/detail/polyapiide/jladdfejldmbglilemedogoeceohbbmb?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client)
- Website: [polyapiclient.ru](https://polyapiclient.ru?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) (подойдут и другие браузеры на Chromium, в том числе Microsoft Edge): клиент для запросов к API (программный интерфейс приложения) **прямо во вкладке браузера**. Это не десктоп-программа и не обязательное облако.

Коллекции (папки сохранённых запросов), окружения и ответы по умолчанию живут на вашем компьютере. Чтобы отправить запрос на тарифе Free, аккаунт на сайте не нужен.

**English.** PolyApiIDE is a **Chrome extension**, not a desktop app. Send requests and keep collections on the device; no mandatory account. This repository is the official product page and does **not** contain source code.

- Install (canonical): [Chrome Web Store — PolyApiIDE](https://chromewebstore.google.com/detail/polyapiide/jladdfejldmbglilemedogoeceohbbmb?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client)
- Website: [polyapiclient.ru](https://polyapiclient.ru?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client)

---

## Установить

1. Откройте карточку в магазине Chrome (каноническая ссылка):  
   **[chromewebstore.google.com/detail/polyapiide/…](https://chromewebstore.google.com/detail/polyapiide/jladdfejldmbglilemedogoeceohbbmb?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client)**
2. Нажмите «Добавить в Chrome».
3. Откройте расширение с иконки на панели, создайте запрос или импортируйте коллекцию, нажмите Send.

Сайт, тарифы и список форматов: [polyapiclient.ru](https://polyapiclient.ru?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) · [быстрый старт](https://polyapiclient.ru/quick-start?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) · [возможности](https://polyapiclient.ru/features?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client)

В Edge и других Chromium-браузерах открывается та же страница магазина Chrome.

---

## Скриншоты

Снимки с официального сайта (в этом репозитории разработки готовых PNG для витрины нет).

![Рабочее место на Free](https://polyapiclient.ru/demo/shots/overview-free.png?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client)

![Платные разделы в том же окне](https://polyapiclient.ru/demo/shots/overview-lifetime.png?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client)

Чтобы README не зависел от сайта, положите те же файлы **рядом с этим README** в публичном репозитории и замените ссылки на относительные:

```markdown
![Free](./overview-free.png)
![Paid](./overview-lifetime.png)
```

---

## Что умеет

- Запросы REST, GraphQL, WebSocket, SOAP; **gRPC — через JSON** (шлюз / transcoding), не нативный бинарный канал
- Несколько пространств (workspaces), коллекции, окружения, переменные вроде `{{baseUrl}}` и `{{token}}`
- Скрипты до и после отправки в песочнице (объекты `poly` и `pm`)
- Импорт уже существующих коллекций — см. тарифы ниже
- Интерфейс на русском и английском, светлая и тёмная тема

На сервер уходит только то, что вы сами включили: ключ, ручной бэкап, история помощника, обращение в поддержку.

---

## Free и платное — без вранья

**Free** (ключ не нужен): коллекции, отправка запросов, скрипты, **Импорт OpenAPI, WSDL, GraphQL, .proto, AsyncAPI, Postman, curl, Insomnia, Hoppscotch, Thunder** (примеры: https://polyapiclient.ru/examples).

**Актуальный список фич сверяйте на [сайте](https://polyapiclient.ru/features?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client)** — витрины могли расходиться.

**Месяц, Год и Lifetime** открывают сценарии проверок (QA), прогон нагрузки с отчётом (в том числе PDF), прокси, помощника с вашим ключом модели, патчи коллекций, бэкап и отправку задачи в трекер или мессенджер.

Оплата и ключи — на [polyapiclient.ru](https://polyapiclient.ru?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client), через ЮMoney, **не** через магазин Chrome.

**Lifetime** — замороженная сборка на дату покупки: ключ и архив конкретной версии, без обещания всех будущих релизов. Если нужны новые функции после покупки — тарифы Месяц или Год.

Цены сюда не копируем: они меняются, смотрите сайт.

---

## Чего нет (чтобы не было сюрприза)

- **Нет git-папки.** Коллекции не лежат обычными файлами в репозитории, как у Bruno. Они живут в хранилище Chrome; обмен — экспорт, импорт или патч руками.
- **Нет CLI** (интерфейс командной строки). Нельзя честно обещать прогон в пайплайне, как Newman или `bru`.
- **Нет MCP** (Model Context Protocol — стандарт, которым ИИ-редактор вызывает инструменты). Есть чат с вашим ключом модели; это другое.
- Нагрузка идёт **из браузера**. Это не замена k6 или JMeter на больших RPS (запросов в секунду).
- **gRPC через JSON**, не нативный protobuf / HTTP/2.

---

## Когда какой инструмент

- Коллекции **файлами в Git** и ревью как у кода — **Bruno**.
- Облако команды, мониторы по расписанию, роли, прогон в CI — **Postman**.
- Уже живёте в редакторе кода — Thunder Client или REST Client.
- Нужна вкладка браузера без нашего расширения — Hoppscotch.
- Нужен клиент **в Chrome**, без обязательного аккаунта, с отчётом QA и оплатой из РФ — узкий слот **PolyApiIDE**, с минусами выше.

Мы не «убийца Postman» и не замена Bruno, а альтернатива в РФ.

---

## Ссылки

| | |
|---|---|
| Установка | [Chrome Web Store](https://chromewebstore.google.com/detail/polyapiide/jladdfejldmbglilemedogoeceohbbmb) |
| Сайт | [polyapiclient.ru](https://polyapiclient.ru?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) |
| Быстрый старт | [polyapiclient.ru/quick-start](https://polyapiclient.ru/quick-start?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) |
| Возможности и тарифы | [polyapiclient.ru/features](https://polyapiclient.ru/features?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) |
| Сравнение с Postman | [polyapiclient.ru/compare](https://polyapiclient.ru/compare?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) |
| Вопросы и ответы | [polyapiclient.ru/faq](https://polyapiclient.ru/faq?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) |
| Конфиденциальность | [polyapiclient.ru/privacy](https://polyapiclient.ru/privacy?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) |
| Соглашение | [polyapiclient.ru/terms](https://polyapiclient.ru/terms?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) |
| Поддержка | [polyapiclient.ru/support](https://polyapiclient.ru/support?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) · support@polyapiide.ru |

Если в этом репозитории включены Issues — туда можно писать баг или хотелку. Оплата и ключи только через сайт.

---

## English

PolyApiIDE is an **official product page** for a proprietary Chrome extension (Chromium / Edge use the same Chrome Web Store listing). **No source code is published here.**

**Install:** [Chrome Web Store](https://chromewebstore.google.com/detail/polyapiide/jladdfejldmbglilemedogoeceohbbmb?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) · **Site:** [polyapiclient.ru](https://polyapiclient.ru?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) · [EN quick start](https://polyapiclient.ru/en/quick-start?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client)

**Free:** collections, send, scripts, Postman and cURL import. No site account required. The website may list additional spec formats on Free; the store listing is more conservative. **Check [polyapiclient.ru/features](https://polyapiclient.ru/features?utm_source=github&utm_medium=readme&utm_campaign=poly-api-client) for the current list.**

**Paid (Month / Year / Lifetime):** QA check scenarios, browser-side load runs with a report, proxy, an assistant that uses *your* model key, collection patches, backup, tracker/messenger handoff. Keys are sold on the website (currently YuMoney / Russia), not through the store. **Lifetime is a frozen build** as of the purchase date — not every future release.

**Not included:** Git-on-disk collections, CLI / CI runner, MCP tool server, native gRPC, k6-class load. OAuth in the IDE is “paste an already-issued token”, not a full authorization-code + PKCE login.

**Pick Bruno** if you need collections as Git files. **Pick Postman** if you need cloud team workspaces and monitors. **Pick this** if you want a Chrome tab, local-first Free send, QA reports, and billing that works from Russia.

---

Это официальная страница продукта PolyApiIDE, не зеркало и не форк. Код расширения в этот репозиторий не выкладывается.
