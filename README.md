# Laravel 11 + Vue 3: Laravel API
Example of a decoupled integration between Laravel and a Vue application packed with Vite. This is the backend component of the system in the form of a Rest API developed using Laravel 11.

## Main steps

### Expose API routes:
```bash
php artisan install:api
```

### Enabled CORS policy to allow the frontend access to the API endpoints:

* Publish CORS config:
```bash
php artisan config:publish cors
```
* Setting up an environment variable in `.env` to stablish the frontend app url in order to grant CORS access:
```yml
CORS_ALLOWED_ORIGINS="http://localhost:5173"
```
* Loading the frontend url from `.env` and adding it to `allowed_origins` in the CORS config file located in `config/cors.php`:
  
```php
'allowed_origins' => explode(',', env('CORS_ALLOWED_ORIGINS', '*')),
```



## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
