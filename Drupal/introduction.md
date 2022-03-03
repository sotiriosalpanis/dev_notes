# Introduction to Drupal

**Based on the drupalize me user guide 'Prerequisite knowledge' section [https://drupalize.me/tutorial/user-guide](https://drupalize.me/tutorial/user-guide)**

- Drupal is a CMS, and has traditionally been built on the LAMP stack

## Modules

- set of PHP, JS and/or CSS files that extend the site features and add functionality
- turn on func/feat by installing module
- site performance is affected, so uninstall unneeded modules
- core download includes these modules:
  - User
  - Node
  - Menu UI
  - Views and Views UI

## Themes

- themes provide a set of named regions: areas on a page for content to be added
- Content region is the only required region for any theme

## Types of data

### 1.Content

- information that is intended for display to site visitors
- relatively permanent, but can be edited

### 2.Configuration

- info about the site that is not content, but also relatively permanent and defines how the site behaves or is displayed

### 3.State

- temp into about the current state of the site e.g. when cron jobs were last run

### 4.Session

- info about the individuals interaction with the site, are they logged in and their cookies. Also temporary.

## Requirements

### - Disk space

- minimum 100MB for core files

### - PHP

- 7.3 or higher

### - Web server

- Apache is recommended, but Nginx is also common

### - Database

- Use one of the following:
  - MySQL
  - PostgreSQL
  - SQLite
