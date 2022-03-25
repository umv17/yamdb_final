![Yamdb Workflow Status](https://github.com/umv17/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg?branch=master&event=push)
# API_YAMDB
Проект для сервиса YaMDb — сбор отзывов о фильмах, книгах или музыке.

## Описание

Проект YaMDb собирает отзывы пользователей на произведения.
Произведения делятся на категории: «Книги», «Фильмы», «Музыка» и т.д.

### Пример сервера
[Пример сервера](https://umika.ddns.net/admin/)

### Документация по проекту API YaMDb

После установки будет доступна по адрессу : http://localhost/redoc/


### Запуск проект:

Клонируем репозиторий и переходим в него:
```bash
git clone https://github.com/umv17/infra_sp2
```

Переходим в папку infra с файлом docker-compose.yaml

Собираем контейнеры:
```bash
docker-compose up -d --build
```

Выполняем миграции:
```bash
docker-compose exec web python manage.py makemigrations
```
```bash
docker-compose exec web python manage.py migrate
```

Создаем суперпользователя:
```bash
docker-compose exec web python manage.py createsuperuser
```

Собираем статику:
```bash
docker-compose exec web python manage.py collectstatic --no-input
```

Создаем дамп базы данных:
```bash
docker-compose exec web python manage.py dumpdata > dumpPostrgeSQL.json
```

### Пример шаблона для подключения базы данных .env неоходимо расположить в каталоге infra/.env
```
DB_ENGINE=django.db.backends.postgresql
DB_NAME=postgres
POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
DB_HOST=db
DB_PORT=5432
```

### Автор:
Михаил Унжаков
