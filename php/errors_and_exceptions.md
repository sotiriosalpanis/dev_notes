# Errors and exceptions

- php 'exception-light', which means it'll try to keep progressing regardless of what happens

## Error severity

- three most common:
  - errors (`E_ERROR`): fatal run-time errors, stop PHP executing
  - notices (`E_NOTICE`): advisory messages, may or may not cause problems, code still executes
  - warnings (`E_WARNING`): non-fatal errors, code still executes

## Changing PHP's error reporting behavior

- can be modified in PHP settings and/or function calls
- built-in function `error_reporting()` you can set error levels
- e.g. if you only want to see Errors and Warnings (no Notices):

```php
<?php
error_reporting(E_ERROR | E_WARNING)
```

## Inline error suppression

- error control operator `@` e.g.

```php
<?php
echo @$foo['bar']
```

## ErrorException

- use the `ErrorException` class to throw error as exceptions

**Docs: [https://www.php.net/class.errorexception](https://www.php.net/class.errorexception)**

## Exceptions

- PHP is fairly lax with returning Exceptions, and will often just fail silently
- Exceptions should be thrown to make a developer aware of an error so that they can choose how to handle it
- SPL provides extension of standard exceptions, and they're recommended to use
