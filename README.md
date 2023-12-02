### Описание:

API для Yatube.

#### Функционал:

* Подписка и отписка от авторизованного пользователя;
* Авторизованный пользователь просматривает посты, создавёт новые, удаляет и изменяет их;
* Просмотр сообществ;
* Комментирование, просмотр, удаление и обновление комментариев;
* Фльтрация по полям.

#### Документация по адресу:
```
http://localhost:8000/redoc/
```
#### Стек

[![Python](https://img.shields.io/badge/-Python-464641?style=flat-square&logo=Python)](https://www.python.org/)
[![Django](https://img.shields.io/badge/Django-464646?style=flat-square&logo=django)](https://www.djangoproject.com/)

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/Kamstrim/api_final_yatube.git
```

```
cd api_final_yatube
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

### Примеры запросов

Получение токена

Отправить POST-запрос на адрес `api/v1/jwt/create/` и передать 2 поля в `data`:

1. `username` - имя пользователя.
2. `password` - пароль пользователя.

Создание поста

Отправить POST-запрос на адрес `api/v1/posts/` и передать обязательное поле `text`, в заголовке указать `Authorization`:`Bearer <токен>`.

1. Пример запроса:

   ```json
   {
     "text": "Мой первый пост."
   }
   ```
   
2. Пример ответа:

   ```json
   {
     "id": 2,
     "author": "Stas",
     "text": "Мой первый пост",
     "pub_date": "2023-08-09T11:31:22.024183Z",
     "image": null,
     "group": null
   }
   ```

