


## php
- nullsafe operator (`?->`) : shortcut that allows you to access a property or method without checking if the object is null. If the object is null it'll simply return null- avoids wrapping a statement in an `is_null()` check.
```
$result = $repository?->getUser(5)?->name;
```