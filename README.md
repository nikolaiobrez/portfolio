# Личная визитка / портфолио

Одностраничный сайт-визитка: один HTML-файл, без внешних зависимостей. Тёмная тема с бирюзовыми акцентами, анимации, секции: герой, о себе, навыки, контакты.

## Как открыть

Откройте `index.html` в браузере или запустите любой локальный сервер из папки проекта.

## Как сделать репозиторий публичным

1. Создайте новый репозиторий на GitHub (или другом сервисе).
2. Выполните в папке проекта:

   ```bash
   git init
   git add index.html README.md .gitignore
   git commit -m "Initial commit: portfolio site"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
   git push -u origin main
   ```

3. В настройках репозитория включите публичный доступ.

## Как не залить секреты (контакты) в репозиторий

В `index.html` стоят заглушки: `your@email.com`, `t.me/your_username`, `vk.com/your_page`.

- **Вариант A.** Оставьте в репозитории версию с заглушками. Реальные ссылки подставьте только в той копии, которую деплоите (например, на GitHub Pages с другого бранча или через отдельный деплой).
- **Вариант B.** Храните версию с реальными контактами в отдельном файле, который не коммитите:
  - скопируйте `index.html` в `index.local.html`;
  - замените в `index.local.html` email и ссылки на соцсети;
  - файл `index.local.html` уже добавлен в `.gitignore` и не попадёт в репозиторий.

В публичный репозиторий добавляйте только версию с заглушками или без реальных контактов.

## Деплой на Vercel (автодеплой при push в master)

При каждом `git push` в ветку `master` сайт автоматически деплоится на Vercel через GitHub Actions.

**Однократная настройка:** добавьте в репозиторий GitHub секрет:
1. GitHub → репозиторий **portfolio** → Settings → Secrets and variables → Actions.
2. New repository secret: имя `VERCEL_TOKEN`, значение — [токен из Vercel](https://vercel.com/account/tokens) (Create Token).

После этого любой `git push origin master` запускает деплой; продакшен-URL проекта: https://portfolio-eta-seven-lh1a6fq5rj.vercel.app
