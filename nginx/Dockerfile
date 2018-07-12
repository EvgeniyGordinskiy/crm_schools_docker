FROM nginx:latest
RUN groupadd -g 48 apache && useradd -d /home/apache -u 48 -g 48 apache
COPY ./nginx.conf /etc/nginx/nginx.conf
COPY ./default.conf /etc/nginx/conf.d/default.conf

