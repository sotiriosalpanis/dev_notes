# Basic Site Configuration

## Administrative Overview

#### Admin menu

- available to users with appropriate permissions
- menu links vary between different sites
- top-level links are:
  - content
  - structure
  - appearance
  - extend
  - configuration
  - people
  - reports
  - help

### Configuring the basic site info

- in the Manage admin menu: *Configuration > System > Basic site settings* to change the site name, slogan, admin email address, or the default front page path

### Configuring default regional settings

- Manage menu: *Configuration > Regional and language > Regional settings*

## Installing a module

### Using the admin interface

- Manage menu: *Extend* shows all available modules in your site
- check boxes for modules to install and press Install

### Using Drush

- Manage menu: *Extend* shows all available modules in your site
- Find the machine name of the module you want to install: expand the info area of the module
- Run command to install

```sh
drush pm:{machine name}
```

## Uninstalling unused modules

### Using the admin interface

- Manage menu: *Extend > Uninstall* check boxes and click *Uninstall*

### Using Drush

- Manage menu: *Extend* shows all available modules in your site
- Find machine name and run:

```sh
drush pm:uninstall tracker
```

## Config user account settings

- Manage menu: *Configuration > People > Account settings*
- Under *Registration and cancellation* select 'Administrators only'
- Update 'Notification email address'
- Can also update the email templates, for automated emails sent when people register etc.

## Configuring the theme

- Manage menu: *Appearance*
- Select theme - *Set as default*
- Under theme click *Settings* and customise
