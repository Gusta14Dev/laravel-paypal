## laravel-paypal for Laravel 8

`laravel-paypal for laravel 8.x` is a fork of `laravel-paypal` only compatible with laravel 8. So this project is just a VCS for the library to be compatible with Laravel in version 8.x.

For more information about the package, see the official package: https://github.com/net-shell/laravel-paypal 

## Installation

1. In your composer.json add
```json
"require": {
        "gusta14dev/paypal": "*"
    },
 "repositories": [
        {
            "type": "vcs",
            "url": "https://github.com/Gusta14Dev/laravel-paypal"
        }
 ],
 ```

2. Next, add the service provider to `app/config/app.php` in the `providers` array.

```php
'providers' => array(
    // ...
    Netshell\Paypal\PaypalServiceProvider::class,
)
```

3. Finally, add an alias to `app/config/app.php` in the `aliases` array.

```php
'aliases' => array(
    // ...
    'Paypal' => Netshell\Paypal\Facades\Paypal::class,
)
```
##For more information

For the use of the package see the link of the official repository.
