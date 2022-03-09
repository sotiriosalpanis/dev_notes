# Define module permissions

- permissions page: *People > Permissions*

## Static permissions

- simplest type of permissions for a custom module
- values are fixed
- specified in a YAML file: `MODULENAME.permissions.yml`
- yaml fule uses the permission name as the key and contains additional options for the value e.g.

```yml
'delete contact entity':
  title: Delete entity content
'add contact entity':
  title: Add entity content
'view contact entity':
  title: View entity content
'edit contact entity':
  title: Edit entity content
'administer contact entity':
  title: Administer settings
```

- the keys are what will be checked for in the code, while the `title:` value is what will be rendered on the permissions page
- e.g. with additional keys:

```yml
'administer contact entity':
  title: Administer settings
  description: Allows user to alter settings related to contacts
  restrict access: TRUE
```

## Dynamic permissions

- allows permissions for a module to be set dynamically, e.g. a user can update their own posts but someone else's
- use the `permissions_callbacks` key in `permissions.yml` file e.g.

```yml
delete all revisions:
  title: 'Delete all revisions'
  description: 'Role requires permission to <em>view revisions</em> and <em>delete rights</em> for nodes in question or <em>administer nodes</em>.'

permission_callbacks:
  - \Drupal\node\NodePermissions::nodeTypePermissions
```

- `nodeTypePermissions` is used as a permissions callback
