# Upgrade Guide

## Upgrading to Breeze (Laravel 13 & Tailwind v4 Edition)

This version of Breeze introduces significant updates to align with Laravel 13 and Tailwind CSS v4.

### PHP 8.3 Required

Laravel 13 requires **PHP 8.3** or higher. Before upgrading, ensure your environment and `composer.json` are updated to reflect this requirement.

### Laravel 13 Framework Changes

#### CSRF Middleware Rename
In Laravel 13, the `VerifyCsrfToken` middleware has been renamed to `PreventRequestForgery`. If you have customized this middleware or reference it in your `bootstrap/app.php`, you should update the class reference:

```php
use Illuminate\Foundation\Http\Middleware\PreventRequestForgery;

// ...
```

### Tailwind CSS v4 Migration

Breeze now utilizes **Tailwind CSS v4**, which moves away from JavaScript-based configuration.

#### Configuration Files
The `tailwind.config.js` and `postcss.config.js` files are no longer required and have been removed from the default scaffolding.

#### CSS-First Configuration
Configuration is now handled directly in your CSS entry point (typically `resources/css/app.css`):

- **Imports**: Use `@import "tailwindcss";` instead of the old `@tailwind` directives.
- **Theme**: Use the `@theme` block to customize your design tokens (e.g., fonts, colors).
- **Plugins**: Use the `@plugin` directive to load official plugins like `@tailwindcss/forms`.

#### Vite Integration
The `@tailwindcss/vite` plugin is now used in `vite.config.js`. Ensure your Vite configuration includes this plugin for optimal performance.

### Automated Upgrades

As Breeze is a starter kit, the recommended way to "upgrade" an existing application is often to review the changes in the latest stubs and manually apply them to your project, or use a tool like **Laravel Shift**.

If you are starting a new project or re-running the installation:
1. Update your `laravel/breeze` dependency.
2. Run `php artisan breeze:install [stack]`.
3. Note that this will overwrite existing views and controllers, so ensure you have a backup or are using version control.
