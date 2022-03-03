# Local development guide

Step-by-step process for setting up local environment for developing Drupal

*N.B.* this guide assumes you're working on MacOS.

## Requirements

- Docker is installed
- composer is installed
- have a db created and set-up ([mysql setup](database_setup.md))

## Local dev with DDEV

- install using homebrew:

```sh
brew install drud/ddev/ddev
```

**DDEV docs: [https://ddev.readthedocs.io/en/stable/](https://ddev.readthedocs.io/en/stable/)**

## Configure local environment to serve application

- Run following command, but replace `my-site-name` with a valid site name:

```sh
export SITE_NAME=my-site-name
mkdir $SITE_NAME
cd $SITE_NAME
ddev config --docroot web --project-name $SITE_NAME --project-type drupal8 --create-docroot
```

*N.B.* this command creates a drupal 8 project, it can be used to create other versions

- creates a new DDEV project, configured to host a Drupal application. DDEV will store the config in a `.ddev` subdirectory
- once configuration is complete, run `ddev start` *N.B.* ensure that Docker is running before running command

## Create a new Drupal application

- run the following commands to create a new Drupal app and install [Drush](https://www.drush.org/latest/):

```sh
ddev composer create "drupal/recommended-project"
ddev composer require drush/drush
```

- next add Drush to the project dependencies

```sh
ddev composer require drush/drush
```

## Install Drupal

- install using Drush, which populates your application's new database:

```sh
ddev drush site:install --account-name=admin --account-pass=password
```

## Launch and login

- use `ddev launch` to launh your new drupal site in a browser, and log in
- if brwoser doesn't launch automatically `ddev describe` will return the URL
