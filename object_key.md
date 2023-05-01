# Here's an implementation in Python that uses recursion to traverse the nested object and retrieve the value associated with the given key:

```python
def get_value(obj, key):
    keys = key.split("/")
    current_obj = obj
    for k in keys:
        current_obj = current_obj.get(k)
        if current_obj is None:
            return None
    return current_obj
```

Here's how you can use the function with the examples provided:

```python
object1 = {"a":{"b":{"c":"d"}}}
key1 = "a/b/c"
value1 = get_value(object1, key1)
print(value1)  # Output: d

object2 = {"x":{"y":{"z":"a"}}}
key2 = "x/y/z"
value2 = get_value(object2, key2)
print(value2)  # Output: a
```

In the function `get_value`, we first split the key string into a list of individual keys using the separator "/", and then use a loop to traverse the nested object one level at a time. We use the `get` method to retrieve the value associated with each key, which returns `None` if the key does not exist in the current level of the object. If we encounter a `None` value, we immediately return `None` to indicate that the key does not exist in the object. If we successfully traverse all the levels of the object, we return the final value associated with the key.
