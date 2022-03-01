<!-- Based on notes taken from php the right way https://phptherightway.com/#language_highlights -->

# Language Highlights

php is flexible and dynamic

## Object oriented programming (OOP)

- supports classes, abstract classes, interfaces, inheritance, constructors, cloning and exceptions.

### Classes

- instantiate with keyword `class`
- can contain it's own constants, variables ('properties') and functions ('methods')
- pseudo variable `$this` is used when a method is called from within an object context.
- `new` used to instantiate class instance
- properties and methods can have the same name (exist in sep namespaces), therefore distinguished by the way they are called i.e. `$obj->bar` vs `$obj->bar()`
e.g.

```php
<?php
class SimpleClass
{
    // property declaration
    public $var = 'a default value';

    // method declaration
    public function displayVar() {
        echo $this->var;
    }
}
?>
```

**Full documentation for Classes and objects at [https://www.php.net/language.oop5](https://www.php.net/language.oop5)**

## Functional Programming

- first class functions: a function can be assigned to  a variable and invoked dynamically
- higher order functions: functions passed as arguments to other functions
- functions can return other functions
- recursion is also possible, but iteration tends to be favoured
- common e.g. of *higher-order function*: use of built-in `array_filter()` the args of which are an input array and a function that is used as a filter function on each array item:

```php
<?php
$input = array(1, 2, 3, 4, 5, 6);

// Creates a new anonymous function and assigns it to a variable
$filter_even = function($item) {
    return ($item % 2) == 0;
};

// Built-in array_filter accepts both the data and the function
$output = array_filter($input, $filter_even);

// The function doesn't need to be assigned to a variable. This is valid too:
$output = array_filter($input, function($item) {
    return ($item % 2) == 0;
});

print_r($output);
```

### Anonymous functions

- allow for the creation of functions which have no specified name, also referred to as closures
- most useful as the value of callable params
- e.g.

```php
<?php
echo preg_replace_callback('~-([a-z])~', function ($match) {
    return strtoupper($match[1]);
}, 'hello-world');
// outputs helloWorld
?>
```

- e.g. 2 variable assignment

```php
<?php
$greet = function($name)
{
    printf("Hello %s\r\n", $name);
};

$greet('World');
$greet('PHP');
?>
```

**Anonymous functions documentation: [https://www.php.net/functions.anonymous](https://www.php.net/functions.anonymous)**

## Meta Programming

- various forms i.e. Magic Methods, [Reflection](https://www.php.net/intro.reflection) and [Overloading](https://www.php.net/language.oop5.overloading)

### Magic Methods

- special methods that override PHP's default action
- all methods beginning with `__` are reserved for php
- e.g. `__toString()`: method that allows a class to decide how it'll react when treated like a string:

```php
<?php
// Declare a simple class
class TestClass
{
    public $foo;

    public function __construct($foo)
    {
        $this->foo = $foo;
    }

    public function __toString()
    {
        return $this->foo;
    }
}

$class = new TestClass('Hello');
echo $class;
?>
```

- full list of magic methods: `__construct()`, `__destruct()`, `__call()`,`__callStatic()`, `__get()`, `__set()`, `__isset()`, `__unset()`, `__sleep()`, `__wakeup()`, `__serialize()`, `__unserialize()`, `__toString()`, `__invoke()`, `__set_state()`, `__clone()`, and `__debugInfo()`.

**Magic method docs: [https://www.php.net/language.oop5.magic](https://www.php.net/language.oop5.magic)**

## Namespaces

- used to help avoid naming conflicts between different developers/environments
- PSR-4 provides recommended namespace usage/conventions
- provide the ability to shorten or alias particularly long names, for the sake of readability
- provide a way of grouping related classes, functions etc.
- e.g. namespace declaration:

```php
<?php
namespace MyProject;

const CONNECT_OK = 1;
class Connection { /* ... */ }
function connect() { /* ... */ }

?>
```

### PSR-4

**Docs: [https://www.php-fig.org/psr/psr-4/](https://www.php-fig.org/psr/psr-4/)**

- specification for autoloading classes from file pahts
- Fully qualified class name example: `\<NamespaceName>(\<SubNamespaceNames>)*\<ClassName>`
  - MUST have top-level namespace i.e. `\<NamespaceName>`
  - MAY have one or more sub-namespaces i.e. `\<SubNamespaceNames>`
  - MUST have a terminating class name i.e. `\<ClassName>`
- case-sensitive

## Standard PHP Library (SPL)

- provides a collection of classes and interfaces, primarily commonly needed datastructure classes (e.g. stack, queue etc.) and iterators

**Docs: [https://www.php.net/book.spl](https://www.php.net/book.spl)**

## Command Line Interface (CLI)

- useful for automating common tasks, and running your app's code directly without a web GUI
- e.g. `php -i` will return your PHP configuration

## Xdebug

- recommended debug tool
<!-- todo: add Xdebug installation/config guidelines -->
