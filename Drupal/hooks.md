# What are hooks?

- allow modules to extend and alter behavior of Drupal core or another module - without changing the existing code
- specially named functions, called at specific times to alter/add to base behavior
- each hook has a unique name, defined parameters and a return value
- hooks have 3 parts:
  1. name
  2. implementation: custom code from your module that is to be executed
  3. definition: another module specifies the hook's name, which arguments are passed and when it will be called
- any number of modules can implement the same hook, order determined by module weight (equal weight: A-Z)

## A naming convention

- basically hooks are a naming convention
- replace the word `HOOK` with the machine name of a module e.g.

This:

```php
HOOK_entity_load()
```

Becomes:

```php
mymodule_entity_load()
```

## Types of hooks

Three categories:

**Info hooks** hooks that answer a question

- invoked when a Drupal component is gathering information
- e.g. a list of all the items that should be displayed in the toolbar

**Alter hooks** hooks that alter existing data

- suffixed with `_alter`
- invoked to alter previously gathered information
- e.g. `hook_form_alter()`

**Action hooks** hooks that react to an action

- invoked when specific actions are taken to trigger other code to do something based on that code
- e.g. `hook_user_cancel()`
