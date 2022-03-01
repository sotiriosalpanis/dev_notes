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
```
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