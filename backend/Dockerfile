# 1. Imagen base
FROM php:8.2-fpm

# 2. Instalar dependencias del sistema (herramientas necesarias)
RUN apt-get update && apt-get install -y \
    libpq-dev \
    zip \
    unzip \
    git \
    curl

# 3. Instalar extensiones de PHP para conectar con PostgreSQL
# NOTA: El nombre correcto es pdo_pgsql, no pdo_pq
RUN docker-php-ext-install pdo pdo_pgsql

# 4. Instalar Composer desde la imagen oficial
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# 5. Definir el directorio de trabajo dentro del contenedor
WORKDIR /var/www/html