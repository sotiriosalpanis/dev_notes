# Dependency injection

- Removal of hard-coded dependencies, so that they can be changed more easily

## Basic example

- Database class with an adapter:

1. Hard dependency: the adapter is instantiated in the constructor:

```php
<?php
namespace Database;

class Database
{
    protected $adapter;

    public function __construct()
    {
        $this->adapter = new MySqlAdapter;
    }
}

class MysqlAdapter {}
```

2. Refactred using Dependency Injection to loosen the dependency:

```php
<?php
namespace Database;

class Database
{
    protected $adapter;

    public function __construct(MySqlAdapter $adapter)
    {
        $this->adapter = $adapter;
    }
}

class MysqlAdapter {}
```

## Complex problem

### Inversion of control

- organisational control separate from objects i.e. loosening dependencies by controlling and instantiating them elsewhere in the system

### SOLID

#### Single responsibility principle

- each class should only have responsibility over a single part of the functionality provided by the software
- improves code reusability

#### Open/closed principle

- classes/modules/functions etc should be open for extension, but closed for modification
- when new funcitonality is required, we shouldn't need to re-write existing code, but write new code that will be used by that existing code

#### Liskov substitution principle

- child classes shouldn't break the parent class type definitions
- e.g. `FileInterface` interface that defines an `embed()` method, `Audio` and `Video` classes  both implement embed method. Therefore creating a `PDF` class at a later date will allow us to reuse the `embed()` method

#### Interface segregation principle

- no client should depend on methods it doesn't use
- therefore instead of one large monolithic interface, smaller-concept specific interfaces should be used
- e.g. A car or bs class would be interested in a `steeringWheel()` method, but motorcycle/tricycle would not.

#### Dependency inversion principle

- about removing hard-links between discrete classes
- 'depend on abstractions. Do not depend on concretions'
