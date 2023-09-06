---
transition: fade-out
---

# What is Authentication?
Authentication is the process of validating the identity of a registered user or process before enabling access to protected networks and systems.

# Ecosystem Overview
Laravel Offers several packages for authentication
-  **Sessions** - Laravel uses Sessions Services
- **Two Factor Authentication** - Laravel Can implement two factor authentication
# Starter Kits
-  **Laravel JetStream** - RObust starter kit that consumes and exposes Laravel Fortify with beautiful UI powerd by 
   tailwind Css, livewire and inertia
-  **Laravel Breeze** -Simple and minimal implementation of all Laravel Authentication Features eg login, 
  registration etc..
- **Laravel Fortify** - Headless authentication backend for laravel that implements many features eg cookie based auth



<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}

</style>

---
layout:  default 
---
# Getting started with Starter Kits
- Laravel Breeze
```shell
# Install this in a fresh laravel application
composer require laravel/breeze --dev

php artisan breeze:install
# Then select the desired type
# 1) Inertia with vue/react
# 2) Blade
# 3) Api Scaffold
```

- Laravel JetStream
```shell
# Install Breeze Package
composer require laravel/jetstream
# Install Jetstream with Livewire
php artisan jetstream:install livewire
# Install Livewire with Teams Functionality 
php artisan jetstream:install livewire --teams 
#Install Jetstream With Inertia
php artisan jetstream:install inertia
# Install inertia with teams Functionality 
php artisan jetstream:install inertia --teams
# Install inertia with SSR(Server Side Rendering) Support
php artisan jetstream:install inertia --ssr
```

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}

</style>
---
layout: default
---
- Laravel Fortify
```shell
# Install Fortify 
composer require laravel/fortify
# Publish Fortify resources
php artisan vendor:publish --provider="Laravel\Fortify\FortifyServiceProvider"
# Migrate Your database
php artisan migrate
```

- Laravel Sanctum

Laravel sanctum is used to authenticate SPA(Single Page Applications)

```shell
# Install Sanctum
composer require laravel/sanctum
# Publish Vendor files
php artisan vendor:publish --provider="Laravel\Sanctum\SanctumServiceProvider"
# Migrate the database
php artisan migrate

```

```php 
# Now Add Sanctums Middleware in your API Endpoint
'api' => [
    \Laravel\Sanctum\Http\Middleware\EnsureFrontendRequestsAreStateful::class,
    \Illuminate\Routing\Middleware\ThrottleRequests::class.':api',
    \Illuminate\Routing\Middleware\SubstituteBindings::class,
],
```