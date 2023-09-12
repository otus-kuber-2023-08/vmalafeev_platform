FROM nginx:latest

RUN sed -i 's/listen\       80\;/listen\       8000\;/g' /etc/nginx/conf.d/default.conf
RUN sed -i 's/root\   \/usr\/share\/nginx\/html\;/root\   \/app\;/g' /etc/nginx/conf.d/default.conf
RUN sed -i 's/pid\        \/var\/run\/nginx\.pid\;/pid\ \/var\/run\/nginx\/nginx\.pid\;/g' /etc/nginx/nginx.conf
RUN mkdir /app

RUN echo 'Nginx running' \
        >/app/homework.html 

RUN usermod -u 1001 www-data
RUN mkdir /var/run/nginx
RUN chown www-data:www-data /var/cache/nginx/ && \
    chown www-data:www-data /var/run/nginx/  && \
    chown www-data:www-data /app

USER www-data


