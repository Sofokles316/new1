# NotPixel Auth for Telegram

Простая страница авторизации для бота NotPixel через Telegram Login Widget.

## Как это работает

1. Пользователь нажимает кнопку авторизации в боте
2. Бот направляет пользователя на эту страницу
3. Пользователь авторизуется одним кликом через Telegram
4. Данные авторизации передаются обратно в бот
5. Бот получает токены от NotPixel API и авторизует пользователя

## Настройка GitHub Pages

### 1. Создать репозиторий на GitHub

1. Перейдите на [github.com](https://github.com)
2. Создайте новый репозиторий (например, `notpixel-auth`)
3. Загрузите файл `index.html` в корень репозитория

### 2. Настроить GitHub Pages

1. В репозитории перейдите в раздел "Settings"
2. Прокрутите до раздела "GitHub Pages"
3. В разделе "Source" выберите "main" (или "master") ветку
4. Нажмите "Save"
5. После активации вы получите URL вашей страницы (например, `https://username.github.io/notpixel-auth/`)

### 3. Настроить бота для работы с GitHub Pages

1. В коде бота (`simple_bot.py`) найдите строку:
```python
auth_url = f"https://your-username.github.io/notpixel-auth/?user_id={telegram_id}"
```

2. Замените URL на ваш URL GitHub Pages:
```python
auth_url = f"https://ваш-юзернейм.github.io/notpixel-auth/?user_id={telegram_id}"
```

### 4. Настроить бота через BotFather

Для корректной работы Telegram Login Widget нужно настроить домен:

1. Откройте чат с [@BotFather](https://t.me/BotFather)
2. Отправьте команду `/mybots`
3. Выберите вашего бота (@notpxcheckbot)
4. Нажмите "Bot Settings" → "Domain"
5. Добавьте домен вашей GitHub Pages (например, `username.github.io`)

## Преимущества этого подхода

1. Пользователь авторизуется одним кликом без необходимости копировать токены
2. Все API-запросы делаются напрямую из бота, а не из браузера
3. Отсутствие необходимости в серверной логике (Netlify Functions)
4. Простота настройки и поддержки 