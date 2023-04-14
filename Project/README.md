## Документация по проекту

Для запуска необходимо:

1. В директории Project создать файл .env и заполнить его по образцу:

```python
SECRET_KEY=INSERT_SOME_SECRET_KEY
DEBUG=False
DJANGO_ALLOWED_HOSTS=localhost 127.0.0.1 [::1]
POSTGRES_HOST_AUTH_METHOD=trust
DB_ENGINE=django.db.backends.postgresql_psycopg2
POSTGRES_USER=postgres
POSTGRES_PASSWORD=password
POSTGRES_DB=stocks_products
POSTGRES_HOST=postgresql
POSTGRES_PORT=5432
DATABASE=postgres
```

2. Открыть директорию Project в терминале и выполнить сборку и запуск контейнера:

```python
docker-compose -f docker-compose.yml up -d --build
```

Так же нобходимо будет применить миграции:

```python
docker-compose -f docker-compose.yml exec backend python manage.py migrate --noinput
```

И собрать статику командой:

```python
docker-compose -f docker-compose.yml exec backend python manage.py collectstatic --no-input --clear
```
