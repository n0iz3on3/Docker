# Домашнее задание к лекции «Docker»

## Документация по проекту

Для запуска проекта необходимо:

1. Запустить сборку контейнера

```bash
docker build . --tag=test_docker_sp
```

Проверить созданный образ можно командой:

```bash
docker image ls
```

2. Запускаем приложение

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
