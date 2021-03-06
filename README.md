
## Introducing

Laravel error handler package

## Install

Install Via Composer

``` bash
composer require dulat/error-handler
```

Publish vendor

``` bash
php artisan vendor:publish
```

Migrate tables

``` bash
php artisan migrate
```
## Usage

After that register captureException method of App\Exceptions\Handler like this.


``` php

    use Dulat\ErrorHandler\Facades\ErrorHandler;
    ..
    
    class Handler extends ExceptionHandler
    {
        ...
    
        public function report(Exception $exception)
        {
            ErrorHandler::captureException($e);
        }
        ...  
    }
```

To change list of receivers, write your emails at `config/error-handler.php`
```php
return [
    'send_email_to' => [
        'example1@gmail.com',
        'example2@gmail.com',
    ]
];
```