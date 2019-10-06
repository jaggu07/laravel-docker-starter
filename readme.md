## Setup Your Local Server

Project uses Docker as local development environment. You can use any standalone tools like WAMP, MAMP as well.

To start the server locally, you need docker installed. You can run the following command to start the server

`docker-compose up`

_Note: When you the docker-compose for the first time, it will take some time to complete the installation._

Create an alias for the command `docker-compose exec app php` by running the following command.

`echo 'alias phpd="docker-compose exec app php"' >> ~/.bashrc`

Because you are already in the shell, you may need to source it this time by running,

`source ~/.bashrc`

Run composer install to install the dependencies

`phpd /usr/bin/composer install`

After successful completion of the composer installation, run the following commands to setup the laravel app.

```
cp .env.example .env
phpd artisan key:generate
phpd artisan optimize
phpd artisan migrate
phpd artisan passport:install
```
Reference 

https://medium.com/@mazraara/laravel-and-docker-7b6f7187f8f9