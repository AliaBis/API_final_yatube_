README.md
# Яндекс.Практикум
## курс Python-разработчик плюс

### Учебный проект api_final_yatube


#### Задачи проекта:
В проекте должна быть описана модель Follow, в ней должно быть два поля — user (кто подписан) и following (на кого подписан). Для этой модели в документации уже описан эндпоинт /follow/ и два метода:
+ GET — возвращает все подписки пользователя, сделавшего запрос. Возможен поиск по подпискам по параметру search
+ POST — подписать пользователя, сделавшего запрос на пользователя, переданного в теле запроса. При попытке подписаться на самого себя, пользователь должен получить информативное сообщение об ошибке. Проверка должна осуществляться на уровне API.
+ 
Когда вы запустите проект, по адресу `http://127.0.0.1:8000/redoc/` будет доступна документация для API Yatube. В документации описано, как должен работать ваш API. Документация представлена в формате Redoc.

### **Инструкция по установке:**

+ *Клонировать репозиторий и перейти в его папку в командной строке:*

`git clone https://github.com/coherentus/api_yatube`

`cd api_yatube`

+ *Cоздать и активировать виртуальное окружение:*

    + `python3 -m venv venv`

Для *nix-систем и MacOS:

    `source venv/bin/activate`

Для windows-систем:

    `source venv/Scripts/activate`

- *Установить зависимости из файла requirements.txt:*

`python3 -m pip install --upgrade pip`

`pip install -r requirements.txt`

- *Выполнить миграции:*

`cd yatube_api`

`python3 manage.py migrate`

+ *Запустить проект:*

`python3 manage.py runserver`


## Примеры
Для доступа к API необходимо получить токен: Нужно выполнить POST-запрос

`localhost:8000/api/v1/token/`,

 передав поля username и password. 

 API вернет JWT-токен

Дальше, передав токен можно будет обращаться к методам, например:

`/api/v1/posts/ (GET, POST, PUT, PATCH, DELETE)`

При отправке запроса передавайте токен в заголовке 
`Authorization: Bearer <токен>`