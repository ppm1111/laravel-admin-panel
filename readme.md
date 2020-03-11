## Laravel Admin Panel

Laravel Admin Panel ("LAP") is a drop-in admin panel package for Laravel which promotes rapid scaffolding & development.

- [Screenshots](https://imgur.com/a/12mGWNW)

Features:

- CRUD generator
- Demo mode
- Roles & permissions
- Laravel auth integration
- User timezones (automatically set on login)
- Dynamic model fillables (using database table columns)
- Activity logs
- Settings (stored in database)
- Fully responsive (looks great on desktop & mobile)
- AJAX form validation
- Documentation CRUD
- & much more

Packages used:

- [Laravel6](https://laravel.com/)
- [Laravel Datatables](https://github.com/yajra/laravel-datatables)
- [Laravel Nestedset](https://github.com/lazychaser/laravel-nestedset)
- [Parsedown](http://parsedown.org/)

Assets used:

- Custom admin panel layout (inspired by [Nova](https://nova.laravel.com))
- [Bootstrap 4](https://getbootstrap.com)
- [Datatables](https://datatables.net) (with some tweaks for a better UX)
- [FontAwesome 5](https://fontawesome.com)

### Installation

Require via composer:

    composer require ppm1111/laravel-admin-panel

Publish install files:

    php artisan vendor:publish --provider="Kjjdion\LaravelAdminPanel\LapServiceProvider" --tag="install"

This will create the following files:

    config/lap.php
    public/lap/*.*
    resources/views/vendor/lap/*.*
    app/Http/Controllers/Admin/BackendController.php

Add the `AdminUser`, `DynamicFillable`, and `UserTimezone` traits to your `User` model:

    use Kjjdion\LaravelAdminPanel\Traits\AdminUser;
    use Kjjdion\LaravelAdminPanel\Traits\DynamicFillable;
    use Kjjdion\LaravelAdminPanel\Traits\UserTimezone;
    
    class User extends Authenticatable
    {
        use Notifiable, AdminUser, DynamicFillable, UserTimezone;

Run the migrations:

    php artisan migrate

### Logging In

Visit `(APP_URL)/admin` to access the admin panel.

The default admin login is:

    Email Address: admin@example.com
    Password: admin123

