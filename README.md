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
RECEIPT_DEBTORS = 6
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

![Главное меню](https://raw.githubusercontent.com/Vladislav-opto/Shopping_Bot_Final/main/images/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA3.PNG)

4. Пользователь может перейти в меню работы с чеками и добавить чек, следуя инструкциям от бота.

![Работа с чеками](https://raw.githubusercontent.com/Vladislav-opto/Shopping_Bot_Final/main/images/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA1.PNG)

5. Если пользователю ранее сообщили код авторизации, то он может нажать в главном меню кнопку "У меня есть код авторизации". В таком случае ему будет предложено перейти по ссылке и авторизоваться на сайте для дальнейшего указания категорий товаров, которыми он НЕ ПОЛЬЗОВАЛСЯ на мероприятии.

![Веб-форма авторизации](https://raw.githubusercontent.com/Vladislav-opto/Shopping_Bot_Final/main/images/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA5.PNG)

5.1. В случае успешной авторизации пользователю будет предложено выбрать категории товаров, которыми он НЕ ПОЛЬЗОВАЛСЯ.
Обратите внимание - на сайте выводятся только те категории, которые есть в чеке.

![Выбор категорий](https://raw.githubusercontent.com/Vladislav-opto/Shopping_Bot_Final/main/images/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA6.PNG)

6. Если пользователь желает узнать долги по чеку, то он должен нажать в главном меню кнопку "Хочу узнать кто сколько должен".
На что он увидит ответное сообщение от бота в виде списка участников вечеринки и их долга.
Обратите внимание - бот сообщает долги, рассчитывая их по количеству проголосовавших пользователей на сайте.

![Долг](https://raw.githubusercontent.com/Vladislav-opto/Shopping_Bot_Final/main/images/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA4.PNG)

### Структура базы данных в проекте (для наглядности)

![База данных](https://raw.githubusercontent.com/Vladislav-opto/Shopping_Bot_Final/main/images/db_image.jpg)
