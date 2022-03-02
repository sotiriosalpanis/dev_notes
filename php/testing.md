# Testing

- automated tests are best practice, helps ensure that the application doesn't break when making changes

## Test driven development

- failing automated test case is written first, then code is written that will pass it

### Unit testing

- by checking values in and out of various functions and methods, check that internal logic is working correctly
- should create a unit test for each behavior a class/function must have
- at it's most basic, you should make sure errors occur if you send bad arguments, and works if you send valid ones
- [PHPUnit](https://phpunit.de/) is the de-facto testing framework for writing unit tests for PHP applications

### Integration testing

- phase in software testing where individual modules/functions are combined and tested as a group
- occurs after unit testing
- can use many of the same tools used to complete unit testing

### Functional testing

- also known as acceptance testing
- consists of using tools to create automated tests that actually use the application
- e.g. [Selenium](https://docs.seleniumhq.org/)

## Behavior driven development

- two types of BDD:

1. SpecBDD - focuses on technical behavior of code

- write specifications describing how the code behaves (pseudo-code)
- [PHPSpec](https://www.phpspec.net/) framework

2. StoryBDD - focuses on business or feature behaviors

- human-readable stories that describe behavior of the application
- [Behat](http://behat.org/) framework
