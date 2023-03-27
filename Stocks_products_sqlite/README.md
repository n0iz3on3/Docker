# Домашнее задание к лекции «Docker»

## Документация по проекту

Для запуска проекта необходимо:
1. Скопировать репозиторий командой  

```bash
git clone https://github.com/n0iz3on3/Docker.git
```
Далее применить миграции
```bash
python3 manage.py migrate
```

2. Запустить сборку контейнера

```bash
docker build . --tag=test_docker_sp
```

Проверить созданный образ можно командой:

```bash
docker image ls
```

3. Запустить приложение

```bash
docker run -it -d -p 9090:8000 --restart=always test_docker_sp
```

Остановка контейнера:

```bash
docker container ls -a
```

```bash
docker container stop <CONTAINER ID>
```
