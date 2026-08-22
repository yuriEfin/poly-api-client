# Как выложить публичный репозиторий-витрину

**Мнение:** это хорошо только как *отдельный* public-репо (`polyapiide` / `polyapiide-chrome`) без исходников. `restman-extension` public не делать (закрытый код, обфускация Lifetime, ключи). GitHub ≠ сайт и ≠ SEO Хабра.

1. На GitHub: **New repository** → имя `polyapiide` или `polyapiide-chrome` → **Public** → **не** ставить галочки README / .gitignore / License (MIT = люди решат, что код открыт).
2. В пустой репо залить **только** `README.md` из этой папки (кнопка «Add file» в вебе или отдельная пустая папка — **не** `git push` из `restman-extension`, **не** пушить `js/`, zip Lifetime, `.env`, ключи).
3. Settings / About: Topics `chrome-extension`, `api-client`, `postman-alternative`, `rest-client`. Description: «Официальная страница PolyApiIDE — API-клиент в Chrome. Исходников нет.» Issues — вкл., если нужны «баг/хотелка»; выкл., если не готовы отвечать. Discussions не обязательны.

Опционально: PNG с сайта (`/demo/shots/overview-free.png` и `overview-lifetime.png`) положить рядом с README и сменить ссылки на `./….png`. Бейджи downloads/users не ставить. Внутренний README разработки не трогать и сюда не копировать.
