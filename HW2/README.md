Контейнер для REST API использовался из домашнего задания https://github.com/SviatoslavZonov/31drf. 

Скачаваем в папку HW2 директорию с выполненным заданием 31drf
В файле settings.py заменим на sqlite3 postgresql:

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': BASE_DIR / 'db.sqlite3',
    }
}

В файле requests.http указаны примеры запросов из задания "Умный Дом", на которые отвечает приложение.

Запускаем приложение в докере:
docker build -t 3drf-api .
docker run -p 8000:8000 3drf-api