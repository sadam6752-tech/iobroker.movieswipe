# Инструкция по пушу в GitHub

## Текущий статус

✅ Git репозиторий инициализирован  
✅ Все файлы добавлены в commit  
✅ Первый commit создан  
✅ Remote origin настроен на: https://github.com/sadam6752-tech/iobroker.movieswipe.git  

## Вариант 1: Через VS Code (рекомендуется)

1. Откройте директорию `iobroker.movieswipe` в VS Code
2. Откройте Source Control панель (Ctrl+Shift+G)
3. Нажмите на "..." (три точки) → "Push"
4. VS Code попросит авторизоваться через GitHub
5. Следуйте инструкциям для авторизации

## Вариант 2: Через GitHub Desktop

1. Откройте GitHub Desktop
2. File → Add Local Repository
3. Выберите директорию: `iobroker-adapter-movieswipe/iobroker.movieswipe`
4. Нажмите "Publish repository"
5. Выберите аккаунт sadam6752-tech
6. Убедитесь, что имя репозитория: `iobroker.movieswipe`
7. Нажмите "Publish Repository"

## Вариант 3: Через Personal Access Token

1. Создайте Personal Access Token на GitHub:
   - https://github.com/settings/tokens
   - Нажмите "Generate new token (classic)"
   - Выберите scopes: `repo` (полный доступ)
   - Скопируйте токен

2. Используйте токен для пуша:
   ```bash
   cd iobroker-adapter-movieswipe/iobroker.movieswipe
   git push -u origin main
   # Username: sadam6752-tech
   # Password: [вставьте токен]
   ```

## Вариант 4: Настроить SSH ключ

1. Создайте SSH ключ (если нет):
   ```bash
   ssh-keygen -t ed25519 -C "sadam6752@gmail.com"
   ```

2. Добавьте ключ в ssh-agent:
   ```bash
   eval "$(ssh-agent -s)"
   ssh-add ~/.ssh/id_ed25519
   ```

3. Скопируйте публичный ключ:
   ```bash
   cat ~/.ssh/id_ed25519.pub
   ```

4. Добавьте ключ на GitHub:
   - https://github.com/settings/keys
   - Нажмите "New SSH key"
   - Вставьте скопированный ключ

5. Попробуйте пуш снова:
   ```bash
   cd iobroker-adapter-movieswipe/iobroker.movieswipe
   git push -u origin main
   ```

## После успешного пуша

Проверьте репозиторий: https://github.com/sadam6752-tech/iobroker.movieswipe

Должны быть видны все файлы:
- main.js
- package.json
- io-package.json
- lib/
- admin/
- scripts/
- www/

## Следующие шаги после пуша

1. Создать Release v0.1.0 на GitHub
2. Добавить описание и changelog
3. Протестировать установку из GitHub:
   ```bash
   cd /opt/iobroker
   npm install https://github.com/sadam6752-tech/iobroker.movieswipe/tarball/main
   ```
