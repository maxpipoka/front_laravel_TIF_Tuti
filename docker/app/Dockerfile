FROM php:8.2-fpm

# Instalar extensiones necesarias para Laravel y PostgreSQL
RUN apt-get update && apt-get install -y \
    curl \
    libpq-dev \
    zip \
    unzip \
    git \
    && docker-php-ext-install pdo_pgsql

# Instalar Composer
COPY --from=composer:2.6 /usr/bin/composer /usr/bin/composer

# Establecer directorio de trabajo
WORKDIR /var/www/html

# Configurar permisos
RUN chown -R www-data:www-data /var/www/html