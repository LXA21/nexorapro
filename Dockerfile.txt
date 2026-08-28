FROM php:8.2-apache

# Extensiones necesarias para PDO MySQL (usadas en db.php)
RUN docker-php-ext-install pdo pdo_mysql mysqli

# Apache: habilitar mod_rewrite por si hay rutas amigables
RUN a2enmod rewrite

WORKDIR /var/www/html
COPY . /var/www/html/

EXPOSE 80
