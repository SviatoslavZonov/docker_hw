FROM ubuntu:22.04
FROM nginx
RUN apt update
RUN echo Y | apt upgrade
#RUN echo Y | apt install nginx
#RUN echo Y | apt install systemctl
COPY index.html /usr/share/nginx/html/
CMD ["nginx", "-g", "daemon off;"]
#CMD ["nginx"]
