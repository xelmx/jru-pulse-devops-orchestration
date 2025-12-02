# Base PHP image, the foundation
#FROM php:8.2-apache

# Install dependencies, update - package list for Linux OS
# install -y -  system package that PHP and composer need, y is for yes
# git - sometimes needed by composer to pull specific packages
# libzip-dev unzip - required by php PHP zip extension
# && apt-get clean && rm -rf /var/lib/apt/lists/*  - cleans up downloaded package list caches after installation

#RUN apt-get update && apt-get install -y git libzip-dev unzip \
    #&& apt-get clean && rm -rf /var/lib/apt/lists/* 

# Executes command that PHP DOcker image provided to compile and enable PHP extemsion
# pdo (PHP Data Objects) and pdo_mysql are standard, establish a connection between PHP app and MySQL Database
#RUN docker-php-ext-install pdo pdo_mysql zip

# Install Composer
# COPY --from (Multi-stage build concept)
# copies a single file (composer) from a completely separate, temporary Docker image (composer:latest) directly into current image.
# most efficient way to install Composer. Grab the pre-built executable from an official image

# COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

#Sets the default working directory, standard root directory for the Apache web server 

#WORKDIR /var/www/html/

# Copies only the dependency definition files (composer.json and composer.lock) from host machine into containers WORKDIR
# COPY composer.json composer.lock ./

# Execute the composer command to read the files and download all PHP  packages/libraries into vendor/ folder
# RUN composer install --no-dev --optimize-autoloader

# Copy all application files into the containers working directory
# COPY . /var/www/html/

#--- For testing purposes only, minimal Dockerfile to validate the CI/CD pipeline is working correctly ---
# Official PHP image
FROM php:8.2-apache

# Minimal test: just install one extension to prove the build works
RUN docker-php-ext-install pdo

# Simple command to ensure container starts (the push will succeed)
CMD ["echo", "PHP Build Test Succeeded"]