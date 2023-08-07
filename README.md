# Kittygram
Сайт с возможностью публикации фотографий котов и их достижений, доступен по адресу [awesome-kittygram.online](https://awesome-kittygram.online).

## Технологии
- Python
- Django
- Django REST framework
- JavaScript

## Запуск проекта

### Запуск из образа Docker Hub
Для запуска необходимо скачать в папку проекта файл docker-compose.production.yml и запустить его:
```
sudo docker compose -f docker-compose.production.yml up
```
Произойдет скачивание образов, создание и включение контейнеров, создание томов и сети.

### Запуск проекта из исходников GitHub
Клонируем к себе репозиторий:
```
git clone git@github.com:mogubudu/kittygram_final.git
```
Запускаем:
```
sudo docker compose -f docker-compose.yml up
```

### Миграции и сбор статики
```
sudo docker compose -f [имя-файла-docker-compose.yml] exec backend python manage.py migrate

sudo docker compose -f [имя-файла-docker-compose.yml] exec backend python manage.py collectstatic

sudo docker compose -f [имя-файла-docker-compose.yml] exec backend cp -r /app/collected_static/. /static/static/
```

Проект будет доступен локально по адресу [http://localhost:9000/](http://localhost:9000/)