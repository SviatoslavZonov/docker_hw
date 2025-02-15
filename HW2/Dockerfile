# Запускаем из последней версии Ubuntu
FROM ubuntu:latest

# Устанавливаем рабочую директорию
WORKDIR /app

# Обновляем пакеты и устанавливаем зависимости
RUN apt update && apt install -y \
    python3 \
    python3-pip \
    python3-venv \
    sqlite3 \
    git

# Создаем виртуальное окружение
RUN python3 -m venv /app/venv

# Активируем виртуальное окружение и обновляем pip
ENV PATH="/app/venv/bin:$PATH"
RUN pip install --upgrade pip

# Копируем содержимое текущей директории (включая 31drf) в /app
COPY . .

# Устанавливаем зависимости Python в виртуальное окружение
RUN pip install -r 31drf/smart_home/requirements.txt

# Применяем миграции
RUN python3 31drf/smart_home/manage.py migrate

# Открываем порт 8000
EXPOSE 8000

# Запускаем сервер
CMD ["python3", "31drf/smart_home/manage.py", "runserver", "0.0.0.0:8000"]