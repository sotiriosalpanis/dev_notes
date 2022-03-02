# Coding practices

## The basics

### Comparison operators

```php
<?php
$a = 5;   // 5 as an integer

var_dump($a == 5);       // compare value; return true
var_dump($a == '5');     // compare value (ignore type); return true
var_dump($a === 5);      // compare type/value (integer vs. integer); return true
var_dump($a === '5');    // compare type/value (integer vs. string); return false

//Equality comparisons
if (strpos('testing', 'test')) {    // 'test' is found at position 0, which is interpreted as the boolean 'false'
    // code...
}

// vs. strict comparisons
if (strpos('testing', 'test') !== false) {    // true, as strict comparison was made (0 !== false)
    // code...
}
```

### Conditional Statements

#### If statements

e.g. syntax

```php
<?php
function test($a)
{
    if ($a) {
        return true;
    } else {
        return false;
    }
}

// vs.

function test($a)
{
    if ($a) {
        return true;
    }
    return false;    // else is not necessary
}

// or even shorter:

function test($a)
{
    return (bool) $a;
}
```

#### Switch statements

- only compare values and not type
- iterate case by case until a match is found, can provide a default
- without a break (or return in a function) they will continue to evaluate each case
- e.g. syntax

```php
<?php
$answer = test(2);    // the code from both 'case 2' and 'case 3' will be implemented

function test($a)
{
    switch ($a) {
        case 1:
            // code...
            break;             // break is used to end the switch statement
        case 2:
            // code...         // with no break, comparison will continue to 'case 3'
        case 3:
            // code...
            return $result;    // within a function, 'return' will end the function
        default:
            // code...
            return $error;
    }
}
```

### Global namespace

- when using namespace, it is possible that a function you wrote hides an internal function
- fixed by using `\` before the function name
- e.g. syntax

```php
<?php
namespace phptherightway;

function fopen()
{
    $file = \fopen();    // Our function name is the same as an internal function.
                         // Execute the function from the global space by adding '\'.
}

function array()
{
    $iterator = new \ArrayIterator();    // ArrayIterator is an internal class. Using its name without a backslash
                                         // will attempt to resolve it within your namespace.
}
```

### Strings

#### Concatenation

- if the line extends beyond 120 characters, for readability use concatenation
- use either `.=` or just `.`
- e.g. syntax

```php
<?php
$a  = 'Multi-line example';    // concatenating assignment operator (.=)
$a .= "\n";
$a .= 'of what not to do';

// vs

$a = 'Multi-line example'      // concatenation operator (.)
    . "\n"                     // indenting new lines
    . 'of what to do';
```

#### String types:

1. Single quotes i.e. literal strings: don't parse special characters or variables
2. Double quotes: parse variables and special characters e.g. `\n`,`\t`
3. Nowdoc - multiline literal e.g. `<<<'EOD' -multiple lines of text- EOD;`

4. Heredoc - multiline that parse special characters and variables e.g. `<<<EOD -multiple lines of text- EOD `

### Ternary operators

e.g. syntax:

```php
<?php
$a = 5;
echo ($a == 5) ? 'yay' : 'nay';
```

## Date and time

- DateTime class used for date and time related funcitons in php.
- `createFromFormat()` method to convert a raw string to an object
- `new DateTime` to get the current date and time
- e.g. syntax

```php
<?php
$raw = '22. 11. 1968';
$start = DateTime::createFromFormat('d. m. Y', $raw);

echo 'Start date: ' . $start->format('Y-m-d') . PHP_EOL;
```

- `DateInterval` class makes datetime calculations possible
- good to use DateInterval, because it will account for daylight saving and time zone alterations
- e.g. syntax

```php
<?php
// create a copy of $start and add one month and 6 days
$end = clone $start;
$end->add(new DateInterval('P1M6D'));

$diff = $end->diff($start);
echo 'Difference: ' . $diff->format('%m month, %d days (total: %a days)') . PHP_EOL;
// Difference: 1 month, 6 days (total: 37 days)
```

- can also use standard comparisons i.e. greater/less than
- `DatePeriod` is used to iterate over recurring events e.g. syntax:

```php
<?php
// output all thursdays between $start and $end
$periodInterval = DateInterval::createFromDateString('first thursday');
$periodIterator = new DatePeriod($start, $periodInterval, $end, DatePeriod::EXCLUDE_START_DATE);
foreach ($periodIterator as $date) {
    // output each date in the period
    echo $date->format('Y-m-d') . ' ';
}
```

- [Carbon](https://carbon.nesbot.com/) is a popular API extension of the DateTime class

## Design Patterns

- frameworks usually make a lot of the design pattern decisions for you
- three broad categories:
    1. Creational: creation of objects in a manner suitable to the situation
    2. Structural: simplify the way in which relationships between entities are realised
    3. Behavioral: common communication patterns between objects

**Full guidance/docs: [https://phptherightway.com/#:~:text=https%3A//designpatternsphp.readthedocs.io/](https://phptherightway.com/#:~:text=https%3A//designpatternsphp.readthedocs.io/)**

## UTF-8

**Guide here: [https://phptherightway.com/#php_and_utf8](https://phptherightway.com/#php_and_utf8)**

## Internationalisation (i18n) and Localisation (l10n)

- Internationalisation - orgnaise code so that it can be easily adapted for different languages/regions
- Localisation - how adaptation to new languages/regions is managed
- Pluralisation - local rules for making words plural

**Full guide here: [https://phptherightway.com/#i18n_l10n](https://phptherightway.com/#i18n_l10n)**