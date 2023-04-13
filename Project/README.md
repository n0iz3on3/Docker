## Документация по проекту

Для запуска необходимо:

Выполнить сборку и запуск контейнера:

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
