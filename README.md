# docker-cheatsheet

## Образы

`docker images` - список образов

`docker pull IMGAGE` - скачать образ

`docker rmi IMAGE` - удалить образ

## Список контейнеров

`docker ps`
* `docker ps -a` покажет все контейнеры (остановленные)

## Запуск контейнера

`docker run -dp 80:80 IMAGE`

* -d - detach (запуск в бэкграунде)
* -p - port (мап порта хоста и порта контейнера)

## Остановка и удаление контейнера
 
1. `docker stop CONTAINER`
2. `docker rm CONTAINER`
3. ???
3. PROFIT!

## Шелл в контейнер

`docker exec -it CONTAINER /bin/bash`

## Dockerfile

`FROM` - родительский образ

`RUN` - выполнить команду (установить пакеты итд)

`COPY` - скопировать файл с хоста

## Сборка образа

`docker build -t NEW_IMAGE_NAME DOCKERFILE_DIR`

## Docker-compose

```
services:
  service_name: очевидно
    build: DOCKERFILE_PATH
    image: IMAGE_NAME
    container_name: очевидно      
    network_mode: режим сети ("host", "custom_net_name")      
    expose: # мап портов 
      - 80:80
    volumes: # монтируемые файлы/диры      
      - HOST_PATH:CONTAINER_PATH
```

`docker-compose [up|down]` - запуск и остановка


Запуск в фоновом режиме с `-d`
