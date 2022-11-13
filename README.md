# api_final
api final
### Описание
API Yatube имеет следующие возможности: 
Описание (адрес по умолчанию http://127.0.0.1:8000/api/v1/) | Какие методы запросов настроены
---------|--------
Публикации: posts/, posts/{id}/ | GET(list), POST, GET(retrieve), PUT, PATCH, DELETE
Комментарии: posts/{post_id}/comments/, posts/{post_id}/comments/{id}/ | GET(list), POST, GET(retrieve), PUT, PATCH, DELETE
Сообщества: groups/, groups/{id}/ | GET(list), GET(retrieve)
Подписки: follow/| GET(list), POST
JWT-токен: jwt/create/, jwt/refresh/, jwt/verify/| POST
### Технологии
* Python 3.7.9 64-bit
* Django 2.2.16
* sqlparse 0.4.3
### Запуск проекта в dev-режиме
- Установите и активируйте виртуальное окружение

Описание | Команда в терминале
---------|--------
Установка виртуального окружения из корневой папки проекта | python3 -m venv venv
Активация виртуального окружения | source/venv/bin/activate
В виртуальном окружении установите зависимости | pip install -r requirements.txt
Выполните миграции | python3 manage.py migrate

- Запустите django server для проекта

Описание | Команда в терминале
---------|--------
Используя виртуальное окружение запустите сервер из корневой папки проекта где есть файл manage.py | python3 manage.py runserver

Перейдите по адресу: http://127.0.0.1:8000/api/v1/ и наслаждайтесь.

### Примеры запросов

##### Добавление новой публикации в коллекцию публикаций. Анонимные запросы запрещены.

Запрос POST http://127.0.0.1:8000/api/v1/posts/
Request samples:
```json
{
    "text": "string",
    "image": "string",
    "group": 0
}
```

* text (required) string (текст публикации)
* image string or null \<binary>
* group integer or null (id сообщества)

Вывод (Response samples):
``` json
{
    "id": 0,
    "author": "test",
    "text": "test",
    "pub_date": "2019-08-24T14:15:22Z",
    "image": "string",
    "group": 2
}
```

##### Подписка пользователя от имени которого сделан запрос на пользователя переданного в теле запроса. Анонимные запросы запрещены.

Запрос POST http://127.0.0.1:8000/api/v1/follow/
Request samples:
```json
{
    "following": "string"
}
```

* following (required) string (username)

Вывод (Response samples):
``` json
{
    "user": "string",
    "following": "string"
}
```
Подробнее о запросах и примерах можно узнать по адресу http://127.0.0.1:8000/redoc/
### Вы восхитительны!

### Авторы
Михаил и ЯП