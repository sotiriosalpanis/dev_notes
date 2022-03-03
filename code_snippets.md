# Code Snippets Index

A list of useful commands, organised in alphabetical order by language/framework

## bash

- **delete a file** (`rm filename.txt`)
- **delete an empty directory** (`rm -r directory_name`)
- **delete a non-empty directory** (`rm -rf directory_name`)

## Git

- **list branches:** `git branch`
- **delete branch:** `git branch -d {branch_name}`

## php

- **nullsafe operator** (`?->`) : shortcut that allows you to access a property or method without checking if the object is null. If the object is null it'll simply return null- avoids wrapping a statement in an `is_null()` check.

```php
$result = $repository?->getUser(5)?->name;
```
