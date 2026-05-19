# Как выложить в GitHub без кода

Эта папка уже подготовлена как отдельный публичный репозиторий для HR. В ней нет исходного кода проекта.

## 1. Создать новый репозиторий на GitHub

Создай новый пустой репозиторий, например:

```text
vmnorth
```

Не добавляй README, license или `.gitignore` через GitHub UI, потому что они уже подготовлены локально.

## 2. Проверить git состояние

Открой терминал в этой папке:

```bash
cd /Users/viacheslavmurakhin/Downloads/VMNorth.com/hr-github-package
git status
```

В текущем workspace эта папка уже инициализирована как отдельный git-репозиторий. Если ты экспортировал или скопировал папку без `.git`, тогда инициализируй её заново:

```bash
git init
git branch -M main
git add .
git commit -m "Add public portfolio"
```

## 3. Подключить GitHub репозиторий

Замени `YOUR_USERNAME` на свой GitHub username:

```bash
git remote add origin https://github.com/YOUR_USERNAME/vmnorth.git
git push -u origin main
```

## 4. Что отправлять HR

Можно отправить:

- ссылку на live demo: `https://vmnorth.com`
- ссылку на GitHub-репозиторий: `https://github.com/YOUR_USERNAME/vmnorth`
- короткое описание из `docs/HR_SUMMARY_RU.md`

## Проверка перед публикацией

В папке не должно быть:

- `src/`
- `server/`
- `data/`
- `dist/`
- `node_modules/`
- `.env`
- runtime JSON files such as brief submissions, analytics events, auth data, content copy, logs, or profile data
- `package.json`
- `pnpm-lock.yaml`
- Docker/config/runtime файлов

Если они случайно появились, не делай `git add .` до очистки папки.
