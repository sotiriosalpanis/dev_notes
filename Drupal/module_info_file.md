# Drupal module info file

## Create an info file for a module

- each module requires a `MODULE.info.yml` file: helps Drupal recognise that the bundle of code is a module

### Step-by-step guide

1. **Name the module**

    - must start with a letter
    - lowercase letters
    - no spaces
    - < 50 characters
    - unique within the system
    - not be a reserved word

2. **Create a directory**

    - from root of Drupal installation, create directory `modules/custom`

### Required keys in an info file

- minimum set of key:
  - `name` for the module
  - `description` of the module
  - `type` - module or theme
  - `core_version_requirement` semantic version(s) of core compatible with the module

### Basic example

- including these minimum requirements will make the module available on Drupal's installation screen

```yml
name: Hello World
description: A silly example module
type: module
core: 8.x
core_version_requirement: ^8 || ^9
```

- this example is for a module called `hello_world` saved in a file `hello_world/hello_world.info.yml`
- `core` key is required for modules that need to run on sites with versions of Drupal less than `8.7.7`
  - it cannot have a value greater than `9.x`- use `core_version_requirement` instead

### Package key

- allows you to group custom modules together (default is `Other`)

```yml
package: Custom
```

### Dependencies

- `info.yml` file can also specify dependencies (i.e. other modules)
- if dependencies are specified then they must be installed on Drupal before installing the custom module
- e.g. syntax:

```yml
dependencies:
  - drupal: node # use drupal for a core module
  - webform: webform # for a contributed module: `project_name:machine_name`
```

- can also include sub-modules and specify version restrictions
- e.g. syntax:

```yml
dependencies:
  - drupal: node
  - webform: webform (>=8.x-5.x)
  - devel: devel_generate
```

### Point to settings form route with `configure` key

- specifies the route that will be used to navigate to the module's configuration settings form
- link to the form will automatically be added to the module's listing on the Extend page
