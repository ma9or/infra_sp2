# Документация к API проекта Yatube (v1):
## Предисловие
API Yatube реализован как учебный проект по курсу Django REST Framework
программы обучения backend-разработки школы Яндекс.Практикум. 
Целью данной работы является расширения функциональных возможностей
взаимодействия с социальной сетью Yatube.
Этот RESTful API предоставляет полную функциональность для создания и чтения публикаций
и комментариев к ним, оформления подписок на публикации других пользователей.

## Использование конечных точек (endpoints)

- /api/v1/posts/ - endpoint публикаций
- /api/v1/groups/ - endpoint сообществ
- /api/v1/follow/ - endpoint подписок на публикации авторов

## Примеры использования
***Подробная документация доступна по ссылке:***
```
/redoc/
```
### Получение и создание публикаций (GET, POST)
```
/api/v1/posts/
```
### Получение, обновление и удаление публикации (GET, PUT, PATCH, DELETE)
```
/api/v1/posts/1/
```
### Получение и создание комментариев (GET, POST)
```
/api/v1/posts/1/comments/
```
### Получение, обновление и удаление комментария (GET, PUT, PATCH, DELETE)
```
/api/v1/posts/1/comments/1/
```
### Список сообществ (GET)
```
/api/v1/groups/
```
### Информация о сообществе (GET)
```
/api/v1/groups/1/
```
### Информация о подписках и создание подписки (GET, POST)
```
/api/v1/follow/
```
### Получение JWT-токен (POST)
```
/api/v1/jwt/create/
```
### Обновить JWT-токен (POST)
```
/api/v1/jwt/refresh/
```
### Проверка JWT-токена (POST)
```
/api/v1/jwt/verify/
```
## Поиск и пагинация
### Поиск подписок по подстроке имени автора (GET)
```
/api/v1/follow/?search=rom
```
### Пагинация вывода количества постов на странице (GET)
```
/api/v1/posts/?limit=2&offset=4
```

# Как запустить проект:
## Создайте и заполните по образцу .env-файл
```
DB_ENGINE=<...>
DB_NAME=<...>
POSTGRES_USER=<...>
POSTGRES_PASSWORD=<...>
DB_HOST=<...>
DB_PORT=<...>
SECRET_KEY=<...>
```
## Соберите и запустите контейнер с помощью Docker-compose
```
docker-compose build
docker-compose up
```
## Выполните миграции через Docker-compose
```
docker-compose exec web python manage.py makemigrations --noinput  
docker-compose exec web python manage.py migrate --noinput
```
## Соберите через Docker-compose статику
```
docker-compose exec web python manage.py collectstatic --no-input
```
## Создайте суперпользователя
```
docker-compose exec web python manage.py createsuperuser
```
## Заполнить базу начальными данными
```
docker-compose exec web python manage.py loaddata fixtures.json
```


## Используемые технологии
![Alt-Текст](https://img.shields.io/badge/python-3.9-blue)
![Alt-Текст](https://img.shields.io/badge/django-2.2.16-blue)
![Alt-Текст](https://img.shields.io/badge/djangorestframework-3.12.4-blue)
![Alt-Текст](https://img.shields.io/badge/docker-20.10.16-blue)
![Alt-Текст](https://img.shields.io/badge/nginx-1.21.3-blue)
![Alt-Текст](https://img.shields.io/badge/gunicorn-20.0.4-blue)
