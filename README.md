Installation
============

Install composer dependencies

```shell
composer install
```

Then install the required assets:

    ./bin/console assets:install

Then Generate the SSH keys :

``` bash
$ mkdir -p config/jwt
$ openssl genrsa -out config/jwt/private.pem -aes256 4096
$ openssl rsa -pubout -in config/jwt/private.pem -out config/jwt/public.pem
```

Add your database credentials in .env file

```shell
DATABASE_URL=mysql://db_user:db_password@127.0.0.1:3306/db_name
```

Then create database schema :
```shell
php bin/console doctrine:schema:update --force
```

Then start the development server :

``` bash
php -S 127.0.0.1:8000 -t public
```
___________________

Configuration
=============

#### Minimum configuration

Create .env file from .dev.dist 

Add your JWT passphrase to .env file 

``` bash
JWT_PASSPHRASE=your_passphrase
```

