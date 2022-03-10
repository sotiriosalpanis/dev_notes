# Implement any hook

## How to implement a hook

1. Locate the documentation

- documented by the module or subsystem that invokes them in `*.api.php` files
- once you know the name of the hook you'd like to implement find it in the `*.api.php` file, or search for it on [https://api.drupal.org/](https://api.drupal.org/)

2.Copy the function

- copy + paste the function into the `MODULENAME.module` file, so that the code is loaded and available when needed

3.Rename the function

- replace the word `hook` in the name of the function with the machine name of your module
- some hooks have additional tokens that need updating, which are designated by all caps e.g. `hook_form_FORM_ID_alter()`

4.Add custom code

- replace the code in the new function's body with your own custom code

5.Document your hook

- replace the `@docblock` comment with the standard `Implements hook_*()`

## Remember the `use` statements

- when referring to a class in a `MODULENAME.module` file either:
  - add a `use` statement e.g.
  
  ```php
  use \Drupal\Core\Form\FormStateInterface;

  function mymodule_form_alter(&$form, FormStateInterface $form_state, $form_id) {}
  ```

  - use the full class name e.g.

  ```php
  function mymodule_form_alter(&$form, \Drupal\Core\Form\FormStateInterface)
  ```
