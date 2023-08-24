
#Creating a Simple PHP Dockerized Application

##Create a Dockerfile (Dockerfile.txt):

```
FROM php:7.4-apache
WORKDIR /var/www/html
COPY /php /var/www/html
EXPOSE 80
CMD ["apache2-foreground"]
```
**
## Create an index.php File:
**
Inside the php directory, create an index.php file with the following content:

```
<?php
echo "Hello, Docker!";
?>
```
## Build and Run the Docker Image:

Open a terminal and navigate to the directory containing your Dockerfile.txt and php directory. Build the Docker image and run a container based on it using the following commands:

```
docker build -f Dockerfile.txt -t phpapp .
docker run -d -p 8082:80 --name php-application phpapp
```
## View the Result:

Open your web browser and navigate to http://localhost:8082/ to see the "Hello, Docker!" message from your PHP application.



