# Laravel Breeze - Upgrade to Laravel 13 & Tailwind CSS v4

This repository contains a modernized version of **Laravel Breeze**, upgraded to support the latest industry standards: **Laravel 13** and **Tailwind CSS v4**.

## 🚀 Key Changes

### 1. Laravel 13 Upgrade
The application has been aligned with the requirements and conventions of Laravel 13:
- **Minimum PHP Version**: Updated to `^8.3.0`.
- **CSRF Protection**: Updated to the new `PreventRequestForgery` middleware (replacing the renamed `VerifyCsrfToken`).
- **Sanctum Integration**: Refactored `sanctum.php` configuration to use the modern middleware names.
- **Dependency Alignment**: All stubs and installation traits now point to Laravel 13 compatible packages.

### 2. Tailwind CSS v4 Integration
The CSS engine has been completely overhauled to use the new **CSS-first** configuration approach of Tailwind v4:
- **Zero Configuration**: Removed legacy `tailwind.config.js` and `postcss.config.js` files.
- **Vite Plugin**: Switched to the official `@tailwindcss/vite` plugin for faster builds and better integration.
- **CSS Syntax**:
    - Uses `@import "tailwindcss";` for importing the framework.
    - Theme configuration (like the **Figtree** font) is now handled via the `@theme` block in `app.css`.
    - Plugins (like `@tailwindcss/forms`) are loaded using the `@plugin` directive directly in CSS.
- **Tooling**: Updated `prettier-plugin-tailwindcss` to `^0.7.0` and configured `tailwindStylesheet` in `.prettierrc` for accurate utility sorting.

## 🛠 Installation

To use this modernized version of Breeze, simply install the package as usual and run the installation command:

```bash
composer require laravel/breeze --dev

php artisan breeze:install [stack]
```

Supported stacks included in this upgrade:
- **Blade** with Alpine.js
- **Livewire** (Volt)
- **Inertia** (Vue & React, including TypeScript and SSR support)
- **API** only

## 📝 Static Analysis

The project includes **PHPStan** configuration to ensure code quality:

```bash
./vendor/bin/phpstan analyze
```

---

*Note: This is a modified version of Laravel Breeze focused on early adoption of Laravel 13 and Tailwind CSS v4 features.*
