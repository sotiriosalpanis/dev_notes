# Code Snippets Index

A list of useful commands, organised in alphabetical order by language/framework

## bash

- **create a file:** `touch filename`
- **create a file with some text added:** `echo "some text" > filename`
- **delete a file:** `rm filename.txt`
- **delete all files:** `rm *`
- **delete an empty directory:** `rm -r directory_name`
- **delete a non-empty directory:** `rm -rf directory_name`
- **make bash file executable:** `chmod u+x filename.sh`

## Git

- **list branches:** `git branch`
- **delete branch:** `git branch -d {branch_name}`

## php

- **nullsafe operator** (`?->`) : shortcut that allows you to access a property or method without checking if the object is null. If the object is null it'll simply return null- avoids wrapping a statement in an `is_null()` check.

```php
$result = $repository?->getUser(5)?->name;
```

### ssh

- connect to server `ssh -i {path_to_ssh_credentials} -t {server_address}` e.g. `ssh -i $HOME/.ssh/cogapp/images -t ubuntu@54.154.28.242`

### scp

- copy filelist to local file dir `scp -i $HOME/.ssh/cogapp/images ubuntu@54.154.28.242:/images/nms/filelist.txt {path to local dir}`
