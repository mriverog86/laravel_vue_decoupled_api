# Laravel 11 + Vue 3: Laravel API
Example of a decoupled integration between Laravel and a Vue application packed with Vite. This is the backend component of the system in the form of a Rest API developed using Laravel 11.

### Instalation Guide

1. Clone the repository to your workspace:

```shell
git clone https://github.com/mriverog86/laravel_vue_decoupled_api.git
```

2. Move inside the project folder:

```shell
cd laravel_vue_decoupled_api
```

3. Install the project dependencies:

```shell
composer install
```

4. Generate Application Key:

```shell
php artisan key:generate 
```

5. Start development server:

```shell
php artisan serve
```

## Integration Guide

1. The first step is to create a new Laravel project.
```bash
composer create-project laravel/laravel your_app_name
```

2. Install the project dependencies:

```shell
composer install
```

3. Publish API routes:

```bash
php artisan install:api
```

4. Create a testing API endpoint in. Add a new API endpoint Inside `./routes/api.php`:

```php
Route::get("/test-me", function () {
    return 'Hello from Laravel!';
});
```

5. Publish CORS config:
```bash
php artisan config:publish cors
```
6. Setting up an environment variable in `.env` to stablish the frontend app url in order to grant CORS access:
   
```yml
CORS_ALLOWED_ORIGINS="http://localhost:5173"
```

7. Loading the frontend url from `.env` and adding it to `allowed_origins` in the CORS config file located in `config/cors.php`:
  
```php
'allowed_origins' => explode(',', env('CORS_ALLOWED_ORIGINS', '*')),
```

8. Start development server:

```shell
php artisan serve
```

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
