# Laravel Dev Environment with Docker

Setup local Laravel development environment with docker-compose

You can use this repo as a boilerplate to start new Laravel developments.

## Requirements
* [Docker](https://docs.docker.com/get-docker/)

## Install
* Clone this repo
* Run following commands in order
```bash
cd src
```
```bash
docker-compose run --rm composer create-project laravel/laravel .
```
```bash
docker-compose run --rm npm install
```
```bash
docker-compose run --rm npm run dev
```
* Change DB settings in src/.env to the following
```INI
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=homestead
DB_USERNAME=homestead
DB_PASSWORD=secret
```
```bash
docker-compose run --rm artisan migrate
```
```bash
docker-compose up -d --build
```
* Open http://127.0.0.1:8000 and the site should be up and running

## Stopping
```bash
docker-compose down
```

## Starting
```bash
docker-compose up -d --build
```
## Container ports
- **nginx** - `:8000`
- **mysql** - `:3306`
- **php** - `:9000`

## Configs
- **nginx** - `nginx/default.conf`

## Php Modules
You can add php modules in `Dockerfile`
```bash
RUN docker-php-ext-install pdo pdo_mysql {modules_needed}
```