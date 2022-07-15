# Helper function: checks whether a list is consecutive

```python
def check_is_consecutive(l):
    """Checks whether a list of integers begins at 1 and is consecutive

    Args:
        l (list): list of integers

    Returns:
        bool: indicates whether the list of int are consecutive or not
    """
    maximum = max(l)
    if sum(l) == maximum * (maximum+1) /2 : 
            return True
    return False
```
