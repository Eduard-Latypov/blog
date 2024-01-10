# Blog project

## Описание проекта 
 
Blog это блог об известных женщинах мира. (Простите за тавтологию)) 
 
Ресурс позволяет публиковать собственные посты, подписываться на публикации других пользователей,
комментировать, а также добавлять понравившиеся посты в список «Избранное».
 
## Установка и запуск проекта локально

Для того, чтобы запустить сайт локально на своем компьютере, нужно выполнить следующие шаги:

1. Клонировать репозиторий на компьютер:
```
git clone https://github.com/Eduard-Latypov/blog.git
```

2. Перейти в директорию проекта:
```
cd sitewomen
```

3. Cоздать и активировать виртуальное окружение:

```
python -m venv venv

# linux
source venv/bin/activate

# windows
source venv/source/activate
```

4. Создать приложение в Google или Yandex и получить пароль для процедуры привязки почтового 
   SMTP-бэкенда к аккаунту Google или Yandex. Справочная информация по [ссылке](https://kb.synology.com/ru-ru/SRM/tutorial/How_to_use_Gmail_SMTP_server_to_send_emails_for_SRM)

5. Создать файл `.env`:

```
touch .env
```

6. Заполнить файл следующим содержанием:
```
SECRET_KEY=секретная комбинация из одноименного параметра в settings.py
EMAIL_HOST=SMTP сервер (Google или Yandex)
EMAIL_HOST_USER=почта от имени, которой будут отправляться письма клиентам для восстановления пароля
EMAIL_HOST_PASSWORD=пароль, который будет получен после создания приложения в (Google или Yandex)

```

7. Установить зависимости из файла requirements.txt:

```
pip install -r requirements.txt
```

8. Сформировать и выполнить миграции:

```
python manage.py makemigrations

# в случае, если файлы миграций не формируются командой выше, запустить команду
# последовательно с указанием имен приложений users и women в следующем формате
python manage.py makemigrations [имя приложения]

python manage.py migrate
```

9. Создать супер-пользователя:
```
python manage.py createsuperuser
```

10. Собрать статику:
```
python manage.py collectstatic
```

11. Запустить dev-сервер:
```
python manage.py runserver
```

## Технологическй стек

[![Python](https://img.shields.io/badge/-Python-464646?style=flat-square&logo=Python)](https://www.python.org/)
[![Django](https://img.shields.io/badge/-Django-464646?style=flat-square&logo=Django)](https://www.djangoproject.com/)

## Авторы

[Eduard-Latypov](https://github.com/Eduard-Latypov)

