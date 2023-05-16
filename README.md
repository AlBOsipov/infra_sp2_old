# Yamdb
## Yamdb - бэкэнд проект для создания каталога произведений с возможность оставлять комментарии и ставить оценки. Работает с Rest api. Все упаковано в docket контейнер.

### Установка
Склонировать репозиторий на свой компьютер:
```git clone ```
Перейти в папку с проектом:
```cd api_yamdb```
Создать свой .env файл по образцу
*Шаблон наполнения .env файла*
DB_ENGINE=django.db.backends.postgresql
DB_NAME=<Имя базы данных>
POSTGRES_USER=<Имя пользователя бд>
POSTGRES_PASSWORD=<Пароль от БД>
DB_HOST=db
DB_PORT=5432
SECRET_KEY=<секретный пароль django проекта.>

Создать Docker образ:
```docker build -t api_yamdb . ```

Создать все миграции:
```docker-compose exec web python manage.py makemigrations reviews```
```docker-compose exec web python manage.py migrate reviews```
```docker-compose exec web python manage.py migrate```

Создать супер-юзера:
```docker-compose exec web python manage.py createsuperuser```

Скопировать заготовку БД:
```docker-compose exec web python manage.py loaddata fixtures.json```

Проект доступ по адресу:
http://127.0.0.1/admin

Автор: Александр Осипов