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
