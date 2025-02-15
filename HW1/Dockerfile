# Используем образ Nginx как базовый
FROM nginx
RUN apt update

# Копируем наш index.html в стандартную директорию Nginx
COPY index.html /usr/share/nginx/html/index.html

# Открываем порт 80
EXPOSE 80

# Команда для запуска Nginx
CMD ["nginx", "-g", "daemon off;"]