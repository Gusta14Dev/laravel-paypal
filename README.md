## laravel-paypal for Laravel 8

`laravel-paypal for laravel 8.x` is a fork of `laravel-paypal` only compatible with laravel 8. So this project is just a VCS for the library to be compatible with Laravel in version 8.x.

For more information about the package, see the official package: https://github.com/net-shell/laravel-paypal 

## Installation

1. No seu composer.json acrescente
```json
"require": {
        "gusta14dev/paypal": "*"
    },
 "repositories": [
        {
            "type": "vcs",
            "url": "https://github.com/Gusta14Dev/laravel-paypal"
        }
 ],```

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
##Configuration

Use the `$apiContext->setConfig()` method to pass in your PayPal details.
Below is one example of sandbox configuration in a controller constructor:
```php
    private $_apiContext;

    public function __construct()
    {
        $this->_apiContext = PayPal::ApiContext(
            config('services.paypal.client_id'),
            config('services.paypal.secret'));
		
		$this->_apiContext->setConfig(array(
			'mode' => 'sandbox',
			'service.EndPoint' => 'https://api.sandbox.paypal.com',
			'http.ConnectionTimeOut' => 30,
			'log.LogEnabled' => true,
			'log.FileName' => storage_path('logs/paypal.log'),
			'log.LogLevel' => 'FINE'
		));

    }

```

Given you have set your developer information in `config/services.php`:
```
'paypal' => [
	'client_id' => 'Client_ID',
	'secret' => 'Your_secret'
],

```
For the use of the package see the link of the official repository.
