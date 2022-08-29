# The app steps and Errors  faced me with solutions 

## laravel steps :

install XAMPP 

install composer 

check from cmd ..>> php -v -->> composer 

Terminal --> C:\xampp\htdocs> ..>> composer create-project laravel/laravel firstprojlaravel

Terminal --> C:\xampp\htdocs> ..> cd firstprojlaravel

Terminal --> C:\xampp\htdocs\firstprojlaravel> ..>> php artisan serve 
-->> Starting Laravel development server: http://127.0.0.1:8000

-------------------------------------------------------------------------------------------------------------------

# create a new database laravelapi

change the .env file varaibles 
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=laravelapi
DB_USERNAME=root
DB_PASSWORD=
 
mysql -u root -p 

MariaDB [(none)]> CREATE DATABASE db_name ...
                >;
MariaDB [(none)]> use laravelapi

Database changed
MariaDB [laravelapi]> INSERT INTO posts (title, content) VALUES ('John', 'Doe')

Note : on windows there is a defoult DBpassword , dont set a new password in .env file but let the DB_PASSWORD= variable empty
-------------------------------------------------------------------------------------------------------------------------

# Migration ::
provides a way for easily sharing the schema of the database. It also makes the modification of the schema much easier. It is like creating a schema once and then sharing it many times

php artisan migrate

-------------------------------------------------------------------------------------------------------------------------

# Errors with the Solutions 

1) ERROR 1045 (28000): Access denied for user 'root'@'localhost' (using password: YES)

C:\xampp\mysql\bin  --->> add this path to environment variables from advanced system settings 


2) Symfony\Component\HttpKernel\Exception\MethodNotAllowedHttpException: The POST method is not supported ...... 

You can also view your routes using php artisan command
php artisan route:list

php artisan optimize


3) Illuminate\Database\QueryException 

Problem:SQLSTATE[HY000] [1045] Access denied for user 'root'@'localhost' (using password: YES) (SQL: select * from information_schema.tables where table_schema = laravelapi and table_name = migrations and table_type = 'BASE TABLE')


A) The error means Laravel is trying to connect to the database with invalid credentials.
Whenever you make change to the .env file in Laravel you need to reset the cache. You need to run this command:


B) solution of the 1045 error :: 
php artisan optimize

php artisan route:cache 
php artisan route:clear
php artisan config:clear
php artisan cache:clear
php artisan optimize


-----------------------------------------------------------------------------------------------------------------------

# What is laravel Tinker used for?
Laravel Tinker allows you to interact with a database without creating the routes. Laravel tinker is used with a php artisan to create the objects or modify the data. The php artisan is a command-line interface that is available with a Laravel. Tinker is a command tool that works with a php artisan.

php artisan tinker 

$post = new Post;
$post->title ='My new post'
$post->content = 'My post content'
$post->save();

----------------------------------------------------------------------------------------------------------------------

# ARTISAN COMMANDS 
php artisan serve
php artisan make:model Post -m
php artisan make:controller PostsApiController

----------------------------------------------------------------------------------------------------------------------
# the fully synchronous behavior of PHP

Synchronous PHP code is sequential. Individual tasks must be completed before you can start another one. So with synchronous PHP, the CPU can process only one I/O task at a time...

PHP serves requests synchronously. It means that each line of code executes in the synchronous manner of the script. After getting the result from one line it executes next line or wait for the result before jumping to the execution of the next line of code.

https://www.zend.com/blog/why-you-should-use-asynchronous-php

------------------------------------------------------------------------------------------------------------------------------------------------------------
# MVC design patterns

The model-view-controller (MVC) design pattern specifies that an application consist of a data model, presentation information, and control information. The pattern requires that each of these be separated into different objects.

User ---->> controller(mainpulates)----->> Model(update)----->> View 

-------------------------------------------------------------------------------------------------------------------------------------------------------------------
# accessibility and security compliance

https://laravel.com/docs/4.2/security

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Common PHP or web server exploits
# 7 Most Common PHP Vulnerabilities

1) SQL Injection. Probably one of the most common and well-known PHP vulnerabilities is SQLi, and it's a big problem. ...
2) Remote File Inclusion. ...
3) Cross-Site Scripting(XSS) ...
4) Directory Traversal. ...
5) Cross-Site Request Forgery(CSRF) ...
6) Authentication Bypass. ...
7) Session Hijacking.

https://privacyaustralia.net/7-most-common-php-vulnerabilities/

-------------------------------------------------------------------------------------------------------------------------------------------------------------------
# Scalability Design Principles

1) Avoid the single point of failure. ...
2) Scale horizontally, not vertically. ...
3) Push work as far away from the core as possible. ...
4) API first. ...
5) Cache everything, always. ...
6) Provide as fresh as needed data. ...
7) Design for maintenance and automation. ...
8) Asynchronous rather than synchronous.

---------------------------------------------------------------------------------------------------------------------------------------------------------------------
# MIDDLEWARE
How many types of middleware are there in Laravel?

two types
There are two types of Middleware in Laravel. The Global Middleware will run on every HTTP request of the application, whereas the Route Middleware will be assigned to a specific route. The middleware can be registered at app/Http/Kernel.

----------------------------------------------------------------------------------------------------------------------------------------------------------------

# THE TESTS PROGRAMS USED 
1) postman 
2) install the client Rest extension 

------------------------------------------------------------------------------------------------------------------------

# TUTORIALS Links

https://www.youtube.com/watch?v=WDha52dbLWM&list=PL_edDyMvX8wUZcXnUogsjslBuw0M2LVPz&index=1 

https://www.youtube.com/watch?v=RcxvrhQKv8I

