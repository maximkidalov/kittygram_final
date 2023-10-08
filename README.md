# kittygram_final

## О проекте

Проект реализует веб сайт kittigram по адресу: [shittigram.dynnamn.ru](https://shittigram.dynnamn.ru).
Kittygram - это социальная сеть, для любителей кошек. Пользователи могут добавлять фотографии своих котов и смотреть на
котов, добавленных другими пользователями.
В проекте настроены github actions для автотестов и деплоя на сервер.

## Содержание проекта

- kittygram_workflow.yml
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; CI-CD workflow,
  копия
- docker-compose.production.yml &nbsp;&nbsp;&nbsp; docker с загрузкой образов из docker.hub
- docker-compose.yml
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  docker с локальным build образов
- backend
- frontend

<br/>
<br/>


<details close>
<summary><h2 style="display: inline">Запуск проекта локально <h3 style="display: inline">▶️</h3></h2></summary>

Для запуска проекта необходимо иметь на установленные: node.js, python, pip.

### клонировать проект:

```
https://github.com/kluev-evga/kittygram_final.git
```

### frontend:

```shell
cd frontend
npm i
rpm run dev
```

При успешном старте получим react приложение на [127.0.0.1:3000](https://127.0.0.1:3000)

### backend:

```shell
cd backend
python3 -m venv venv

# Linux/macOS:
  source env/bin/activate
# windows:
  source env/scripts/activate

pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```

При успешном старте получим backend приложение на [127.0.0.1:8000](https://127.0.0.1:8000)

</details>




<br/>


<details close>
<summary><h2 style="display: inline">Техническое задание <h3 style="display: inline">▶️</h3></h2></summary>

Настроить запуск проекта Kittygram в контейнерах и CI/CD с помощью GitHub Actions

## Как проверить работу с помощью автотестов

В корне репозитория создайте файл tests.yml со следующим содержимым:

```yaml
repo_owner: ваш_логин_на_гитхабе
kittygram_domain: полная ссылка (https://доменное_имя) на ваш проект Kittygram
taski_domain: полная ссылка (https://доменное_имя) на ваш проект Taski
dockerhub_username: ваш_логин_на_докерхабе
```

Скопируйте содержимое файла `.github/workflows/main.yml` в файл `kittygram_workflow.yml` в корневой директории проекта.

Для локального запуска тестов создайте виртуальное окружение, установите в него зависимости из backend/requirements.txt
и запустите в корневой директории проекта `pytest`.

## Чек-лист для проверки перед отправкой задания

- Проект Taski доступен по доменному имени, указанному в `tests.yml`.
- Проект Kittygram доступен по доменному имени, указанному в `tests.yml`.
- Пуш в ветку main запускает тестирование и деплой Kittygram, а после успешного деплоя вам приходит сообщение в
  телеграм.
- В корне проекта есть файл `kittygram_workflow.yml`.

</details>