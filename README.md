# Laravel5-RBAC
User Roles &amp; Permissions for Laravel 5.2


# Overview
This Package simple glues together laravel-permission and laravel-authorize for in one package giving you all the features and a simple install route to easily get started.

More details here:
* https://github.com/spatie/laravel-permission
* https://github.com/spatie/laravel-authorize


# Installation
## Install with composer
~~~
composer require askedio/laravel5-rbac:dev-master
~~~

## Add to Providers array in config/app.php
~~~
'providers' => [
   Askedio\Laravel5RBAC\Providers\GenericServiceProvider::class,
   ...
~~~

## Migrate
~~~
php artisan vendor:publish --provider="Spatie\Permission\PermissionServiceProvider" --tag="migrations"
php artisan migrate 
~~~


## Serv
~~~ 
php artisan serv
~~~


## Install the role and user
* Browse to http://localhost:8000/install
* No users will create a new user
~~~
admin@test.com
password
~~~

Default role of admin is created and assigned. Use in web routes

## Use in routes
~~~
Route::get('dashboard', [
   'middleware'=> ['web','can:dashboard'],
   'uses' => 'HomeController@index',
]);
~~~



