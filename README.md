# docker-phpapp
Creating and publish a simple php application in docker container

create a docker file with 

FROM php:7.4-apache
WORKDIR /var/www/html
COPY /php /var/www/html
EXPOSE 80
CMD ["apache2-foreground"]

create a index.php in php directory
<?php
echo "Hello, Docker!";
?>


Build and Run the Docker Image
docker build -f Dockerfile.txt -t  phpapp .
docker run -d -p 8082:80 --name php-application phpapp

you can display your page in 
http://localhost:8082/
