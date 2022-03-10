# Define and invoke a new hook

- when developing a module, define new hooks so that the module can be extended
- requires:
  - unique hook name
  - documentation
  - invoke the hook at critical points

## Quick reference

- hooks are invoked using the `module_handle` service implemented `\Drupal\Core\Extension\ModuleHandler`
- accessed via either `module_handler` or `\Drupal::moduleHandler()`
- invoked by:
  - execute hook in every module that implements in `ModuleHandler::invokeAll()`
  - execute per-module, usually by looping over a list of enabled modules `ModuleHandler::invoke()`
  - alter existing data structures using `ModuleHandler::alter()`

## Should I define a hook?
