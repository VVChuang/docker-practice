FROM nginx
MAINTAINER eric7578 <eric7578@ifalo.com.tw>

COPY index.html /usr/share/nginx/html

RUN chown -R www-data /usr/share/nginx/html
RUN sed -i 's/nginx;/www-data;/g' /etc/nginx/nginx.conf
