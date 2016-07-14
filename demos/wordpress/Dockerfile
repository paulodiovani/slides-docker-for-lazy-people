FROM php:apache

# Install dependencies
RUN apt-get update && apt-get install -y \
    mysql-client

# Add php extension
RUN docker-php-ext-install mysqli pdo pdo_mysql
