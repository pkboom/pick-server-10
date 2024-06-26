# Pick Server

This is a server that [laravel-pick](https://github.com/pkboom/laravel-pick) sends data to.

# Installation

```sh
composer setup
```

# Usage

```sh
php artisan vendor:publish --provider="Pkboom\Pick\PickServiceProvider"

# config/pick.pick
return [
    'pick-server' => 'http://pick-server-10.test/webhook',
];
```

After installing [laravel-pick](https://github.com/pkboom/laravel-pick), use `pick()` in your app.

```php
Route::get('/', function () {
    pick(time());
    pick(User::first());
    pick(time());

    return 'calm down';
});
```

Open `pick-server-10.test` and whatever `laravel-pick` sends will appear here.

<img src="image2.png" />

# Update

Check:

-   app/Http/Middleware/VerifyCsrfToken.php
-   routs/web.php
-   resources/views/pick.blade.php
-   config/pick.php

# Install old laravel

```sh
composer create-project laravel/laravel project-name 10.0
```
