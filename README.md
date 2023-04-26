
## API Отзывов на произведения в контейнере

Проект собирает **отзывы** пользователей на **произведения**. Сами произведения в не хранятся, здесь нельзя посмотреть фильм или послушать музыку.

## Стек

- Python

- Djando

- Docker

- DRF

- API

- git

## Функционал сервиса

- Произведения делятся на категории, такие как «Книги», «Фильмы», «Музыка». Например, в категории «Книги» могут быть произведения «Винни-Пух и все-все-все» и «Марсианские хроники», а в категории «Музыка» — песня «Давеча» группы «Жуки» и вторая сюита Баха.
- Благодарные или возмущённые пользователи оставляют к произведениям текстовые отзывы и ставят произведению оценку в диапазоне от одного до десяти, из пользовательских оценок формируется усреднённая оценка произведения — рейтинг 
- Пользователи могут оставлять комментарии к отзывам.


## Запуск проекта

Клонируем репозиторий к себе на ПК

```bash
  git clone git@github.com:EgorFedotov/infra_sp2.git
```

Переходим в дерикторию с проектом

```bash
  cd infra_sp2
  cd api_yamdb
```

Устанавливаем Виртуальное окружение

```bash
  py -3.7 -m venv venv
```

Активируем виртуальное окружение

```bash
  source venv/Scripts/activate
```

Устанавливаем зависимости

```bash
  pip install -r requirements.txt
```

Переходим в папку с файлом docker-compose.yaml

```bash
  cd infra
```

Поднимаем контейнеры

```bash
  docker-compose up -d --build
```

выполнгяем миграции:

```bash
  docker-compose exec web python manage.py makemigrations reviews

  docker-compose exec web python manage.py migrate
```

Создаем суперпользователя

```bash
  docker-compose exec web python manage.py createsuperuser
```

Србираем статику

```bash
  docker-compose exec web python manage.py collectstatic --no-input
```


# В корне дерриктории infa создайте файл .env и добавьте туда:
  - SECRET_KEY
  - DB_ENGINE
  - DB_NAME
  - POSTGRES_USER
  - POSTGRES_PASSWORD
  - DB_HOST
  - DB_PORT


# Документация доступна по адрессу: http://localhost/redoc/

## 🚀 Автор
Егор Федотов


