# Как выложить в GitHub без кода

Эта папка уже подготовлена как отдельный публичный репозиторий для HR. В ней нет исходного кода проекта.

## 1. Текущий репозиторий

Этот пакет уже подключён к публичному GitHub-репозиторию:

```text
https://github.com/WenziLikes/VMNorth.com
```

Создавать новый репозиторий не нужно, если этот адрес открывается и принадлежит тебе.

## 2. Проверить git состояние

Открой терминал в этой папке:

```bash
cd /Users/viacheslavmurakhin/Downloads/VMNorth.com/hr-github-package
git status
```

Если есть изменения, добавь их, сделай коммит и отправь на GitHub:

```bash
git add .
git commit -m "Update VMNorth public project overview"
git push
```

## 3. Если remote сломался

Проверь remote:

```bash
git remote -v
```

Если `origin` отсутствует или указывает не туда, выставь правильный адрес:

```bash
git remote set-url origin https://github.com/WenziLikes/VMNorth.com.git
git push -u origin main
```

## 4. Что отправлять HR

Можно отправить:

- ссылку на live demo: `https://vmnorth.com`
- ссылку на GitHub-репозиторий: `https://github.com/WenziLikes/VMNorth.com`
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
