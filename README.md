# How to create a RPC server

## Creating project

```bash
composer create-project carno-php/skel-rpcd my-project
```

## Importing service SDK

```bash
composer require my-service/sdk
```

## Implements and register

`src/Services/MyService.php`

```php
namespace App\Services;

class MyService extends \Carno\RPC\Server implements \ServiceAPI
{
    public function method()
    {
        // your code
    }
}
```

`registers.php`

```php
return [
    \App\Services\MyService::class,
];
```

## Run service

```bash
./vendor/bin/rpcd server:start --listen=:8080 --debug
```

## Tests service API

```bash
curl -d 'PAYLOAD' http://127.0.0.1:8080/invoke/service/method
```
