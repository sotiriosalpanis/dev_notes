# Dependency management

## Composer and Packagist

- Composer is the standard package management system for PHP
- dependencies should be listed in a `composer.json` file
- Composer will download dep and set-up auto-loading
- Packagist is the official repo for Composer-compatible PHP libraries

**Composer installation guide: [https://getcomposer.org/download/](https://getcomposer.org/download/)**

### Define and install dependencies

-`composer require` adds a project dependency, creates/updates `composer.json` automatically

- `composer init` guides through creation of `composer.json`
- `composer install` will install packages from an existing `composer.json`, additionally add the following to the primary php file to tell PHP to use Composer to autoload:

```php
<?php
require 'vendor/autoload.php';
```

### Updating dependencies

- `composer.lock` stores exact version of packages
- `composer update` will update all packages
- can define version requirements flexibly, which allows controlled updating e.g. requirement `~1.8` means anything newer than 1.8
- the `global` keyword allows you to install packages globally `composer global require phpunit/phpunit`. It creates a `~/.composer` folder for global dependencies.
