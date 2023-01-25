# Проект ShoppingBot (дипломный проект ЛТЛ)

ShoppingBot - телеграмм-бот, который помогает рассчитать долг для каждого участника вечеринки.

## Установка

1. Клонируйте репозиторий с github (`git clone`)
2. Создайте виртуальное окружение (`python -m venv env`)
3. Установите зависимости `pip install -r requirements.txt`
4. Создайте файл `settings.py` в папке `setting_box`
5. Впишите в `settings.py` следующее:
```
CLIENT_SECRET = 'IyvrAbKt9h/8p6a7QPh8gpkXYQ4=' - единый ключ доступа к модулю для работы с ФНС
API_KEY = `ключ от телеграмм-бота`
URL = `ссылка на базу данных`
BOT_ANSWERS = [
    'Пришли чек и они заплатят за это 💵.',
    'Время платить по счетам ⚖️.\nСкидывай чек.',
    'Гадаю по чеку 🔮.\nОтправь его и я все тебе расскажу',
    'Ты долго ждал, час расплаты настал ⌛.\nОтправляй чек',
    ]
MAIN_MENU = 0
ACTIONS_WITH_THE_RECEIPT = 1
MENU_RECEIPT = 2
ADD_CHECK = 3
PHONE_NUMBER = 4
CODE = 5
HEADERS = {
    'Host': 'irkkt-mobile.nalog.ru:8888',
    'Accept': '*/*',
    'Device-OS': 'iOS',
    'Device-Id': '7C82010F-16CC-446B-8F66-FC4080C66521',
    'clientVersion': '2.9.0',
    'Accept-Language': 'ru-RU;q=1, en-US;q=0.9',
    'User-Agent': 'billchecker/2.9.0 (iPhone; iOS 13.6; Scale/2.00)',
}
NALOG_URL = 'irkkt-mobile.nalog.ru:8888/v2'
SECRET_KEY = 'переменная конфигурации Flask'
SQLALCHEMY_TRACK_MODIFICATIONS = False
SQLALCHEMY_DATABASE_URI = `сслыка на базу данных`
```
6. В первой командной строке запустите main_server.py (`python main_server.py`)
7. Во второй командной строке после активации виртуального пространства запустите main_tg_bot.py (`python main_tg_bot.py`)

### Инструкция по применению

1. Пользователь должен отправить команду `/start` для начала общения с ботом.
2. Сразу после этого бот попросит поприветствовать его путем нажатия на кнопку `Привет!`
3. Далее бот показывает главное меню:

(в разработке)

### Структура базы данных в проекте

![База данных](https://raw.githubusercontent.com/Vladislav-opto/Shopping_Bot_Final/main/images/db1.jpg)
