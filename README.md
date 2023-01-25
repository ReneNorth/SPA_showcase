### Документация 
Дока по API - schema.yaml

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

## Развертывание бэка 
cd kittygram_backend
```
Cоздать и активировать виртуальное окружение:

```
python3 -m venv env
```

* Если у вас Linux/macOS

    ```
    source env/bin/activate
    ```

* Если у вас windows

    ```
    source env/scripts/activate
    ```

```
python3 -m pip install --upgrade pip
```

Установить зависимости из файла requirements.txt:

```
pip install -r requirements.txt
```

Выполнить миграции:

```
python3 manage.py migrate
```

Запустить проект:

```
python3 manage.py runserver
```

### Создать пользователя и протестировать API 
Сначала создайте нового пользователя: в djoser это можно сделать POST-запросом на эндпоинт users/,
к которому нужно добавить новый префикс api/. В теле запроса укажите username и password для нового пользователя.

Пример POST запроса на http://127.0.0.1:8000/api/token/login/: 
{
    "username": "admin",
    "password": "adminadmin"
}

В ответ получите токен, с которым надо в дальнейшем делать запросы
Например, в постман можно добавить токен к запросу в Headers
Key: Authorization 
Value: Token <your_token_you_just_recieved>

Добавить кота POST запросом на http://127.0.0.1:8000/api/cats/: 

{
    "name": "testcat1",
    "color": "#000000",
    "birth_year": 2021
}

если кот добавлен, можно двигать в развёртывание фронтэнда

## Развертывание фронта 

идём в cd kittygram_frontend
Установить зависимости:

npm i
Запустить проект:

npm run start

перейти по адресу http://localhost:3000
