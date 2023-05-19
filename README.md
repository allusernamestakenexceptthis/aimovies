<p align="center"><a href="#" target="_blank"><img src="public/images/aimovies.svg" width="400" alt="Aimovies"></a></p>

<div align="center">

[![Testing Aimovies](https://github.com/allusernamestakenexceptthis/aimovies/actions/workflows/laravel.yml/badge.svg)](https://github.com/allusernamestakenexceptthis/aimovies/actions/workflows/laravel.yml)

</div>

# Aimovies (Scaffold version, it doesn't do anything yet)

Aimovies is a laravel based site to showcase ai generated movie posters.  It allows clients to search for posters, getting their details, authenticate, add/delete favorites and request fake posters 

## Installation

### Step 1

Clone this repository
```
git clone https://github.com/allusernamestakenexceptthis/aimovies.git
```

Copy .env.testing to .env

Unix/Mac
```bash
cp .env.testing .env
```

Windows:
```cmd
copy .env.testing .env
```

### Step 2

#### Install via docker (easy)

Prerequisites: 
You need docker to be installed on your system
https://docs.docker.com/engine/install/

Make sure docker service is running

cd into repo root

Start docker from docker compose file 

```bash
docker-compose up -d
```

Install dependencies

```bash
docker-compose exec filmsdb-app composer install --prefer-dist
```

Generate laravel key

```bash
docker-compose exec filmsdb-app php artisan key:generate
```

Restart docker container

```bash
docker-compose down
docker-compose up -d
```

#### Manual install:
You should ensure that your local machine has PHP 8.1 or 8.2 and Composer installed.
If you are using macOS, PHP and Composer can be installed via [Homebrew](https://brew.sh/). 
PHP installations instructions can be found here:

https://www.php.net/manual/en/install.php

Make sure to install php extensions see this:
https://stackoverflow.com/a/40816033/766985

Composer instructions:
https://getcomposer.org/doc/00-intro.md

```bash
composer install --prefer-dist

php artisan serve
```

Or run sail which needs docker running

Unix/Mac:

```bash
./vendor/bin/sail up
```

Windows:

```cmd
vendor\bin\sail up
```

Or install a web server such as nginx and point it to laravel

### Step 3

Generate Key, apply database migration and seed database with samples

```bash
./vendor/bin/sail php artisan key:generate
./vendor/bin/sail php artisan migrate
./vendor/bin/sail php artisan db:seed
```

### step 4

Go to http://localhost

## Version
1.0.0

## Usage

TODO

## License

To be determined.

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
