<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

<p align="center">
<a href="https://github.com/laravel/framework/actions"><img src="https://github.com/laravel/framework/workflows/tests/badge.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

<br>

# Laravel Sail (Docker)

Laravel setup with docker container environment.

1. install laravel sail

```bash
composer require laravel/sail --dev
```

2. install docker services & publish docker-compose.yaml 

```bash
php artisan sail:install
```

3. adding sail command alias

```bash
alias sail='[ -f sail ] && sh sail || sh vendor/bin/sail'
```

4. running laravel sail

```bash
./vendor/bin/sail up
```

or (after adding alias command)

```bash
sail up 
```

5. phpmyadmin service (additional)

```docker
phpmyadmin:
        image: phpmyadmin/phpmyadmin
        links:
            - mysql:mysql
        ports:
            - 8080:80
        environment:
            MYSQL_USERNAME: "${DB_USERNAME}"
            MYSQL_ROOT_PASSWORD: "${DB_PASSWORD}"
            PMA_HOST: mysql
        networks:
            - sail
```

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
