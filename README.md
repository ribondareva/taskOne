# Django Project

Это базовый шаблон проекта Django, полностью готовый к запуску в Docker. Миграции выполняются автоматически при старте контейнера my_app.

## Запуск
1. Клонируйте репозиторий:
   ```bash
   git clone https://github.com/ribondareva/taskOne.git
   cd taskOne
   ```
2. Создайте .env файл:
   ```bash
   cp .env-example .env
   ```
3. Создайте и активируйте виртуальное окружение:
```bash
python -m venv venv
venv\Scripts\activate
```
4. Запустите проект:
   ```bash
   docker-compose up --build
   ```
4. Перейдите в браузер:
   ```bash
   http://localhost:8000
   ```
##  Переменные окружения
Содержимое .env:
```python
SECRET_KEY=your-secret-key
POSTGRES_USER=user
POSTGRES_PASSWORD=passwd
POSTGRES_DB=test_db
POSTGRES_HOST=db
POSTGRES_PORT=5432
```
SECRET_KEY можно сгенерировать командой:
```bash
python -c "from django.core.management.utils import get_random_secret_key; print(get_random_secret_key())"
```
Описание:
* SECRET_KEY — секретный ключ Django, используется для криптографической подписи (например, куки, токены и др.).
* POSTGRES_USER — имя пользователя PostgreSQL, которое будет создано при запуске контейнера.
* POSTGRES_PASSWORD — пароль для пользователя PostgreSQL.
* POSTGRES_DB — имя базы данных, которая будет создана при инициализации.
* POSTGRES_HOST — хост базы данных, внутри Docker Compose ссылается на имя сервиса (в данном случае db).
* POSTGRES_PORT — порт, на котором работает PostgreSQL (по умолчанию 5432).

  
