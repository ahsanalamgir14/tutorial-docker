FROM php:8.1-fpm-alpine

# Install PDO and PDO MySQL extensions
RUN docker-php-ext-install pdo pdo_mysql

# Install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Set the working directory to /var/www
WORKDIR /var/www

# Copy existing application directory contents
COPY . .

USER root

RUN chmod 777 -R /var/www

# Install Laravel dependencies
RUN composer update

# Expose port 80 and start php-fpm server
EXPOSE 80
CMD ["php-fpm"]
