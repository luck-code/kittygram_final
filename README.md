[![Main Kittygram workflow](https://github.com/luck-code/kittygram_final/actions/workflows/main.yml/badge.svg?branch=main&event=push)](https://github.com/luck-code/kittygram_final/actions/workflows/main.yml)
# 🐱 Kittygram

## 📌 Описание
Kittygram — это веб-приложение для публикации и просмотра карточек котиков. 
Пользователи могут добавлять фотографии, указывать информацию о питомцах и просматривать контент других пользователей.

Проект решает задачи:
- хранение и отображение данных
- работа с API (CRUD)
- контейнеризация и деплой через Docker и CI/CD

---

## 🚀 Используемые технологии

### Backend
- Django — веб-фреймворк 
- Django REST Framework — API 
- PostgreSQL — база данных 
- Gunicorn — сервер приложений 

### Frontend
- React — клиентская часть 

### DevOps
- Docker — контейнеризация 
- Docker Compose — оркестрация 
- Nginx — прокси и статика 
- GitHub Actions — CI/CD 

---

## ⚙️ Установка и запуск (локально)

### 1. Клонировать репозиторий
```bash
git clone https://github.com/luck-code/kittygram_final.git
cd kittygram_final

### 2. Создать файл .env
```bash
POSTGRES_DB=django_db
POSTGRES_USER=django_user
POSTGRES_PASSWORD=django_password
DB_HOST=db
DB_PORT=5432
SECRET_KEY=your_secret_key
DEBUG=False

### 3. Запустить контейнеры
```bash
docker compose up --build -d


docker compose exec backend python manage.py migrate
docker compose exec backend python manage.py collectstatic
docker compose exec backend cp -r /app/collected_static/. /static/

### 5. Открыть в браузере
```bash
http://localhost:9000


### 🌐 Продакшен-проект доступен по адресу:
```bash
https://kittygram24.duckdns.org



### Примеры API-запросов. 
Получить список котиков
```bash
GET /api/cats/


Создать котика
```bash
POST /api/cats/
Content-Type: application/json

{
  "name": "Барсик",
  "color": "black",
  "birth_year": 2020
}

Получить одного котика
```bash
GET /api/cats/{id}/

Удалить котика
```bash
DELETE /api/cats/{id}/



### 🧪 Тестирование
```bash
pytest

CI/CD автоматически:

проверяет код (flake8)
запускает тесты
собирает Docker-образы
выполняет деплой


### 📦 Docker образы
iluckcode/kittygram_backend
iluckcode/kittygram_frontend
iluckcode/kittygram_gateway

### Максим
GitHub: https://github.com/luck-code









