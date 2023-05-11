# 2022-07-07-T1155-

Week 27.4 | Thursday, July 07, 2022 | 11:55 AM

Author : [Christopher Evans](https://www.linkedin.com/in/cevans11)

Related :

Source :

Topics : [Python](../Python.md)

## Q : What does this do?

```python
def with_mystery(p):
    def wrapper(fn):
        def closure(*args, **kwargs):
            import sys
            orig = sys.path[:]
            sys.path.insert(0, p)
            try:
                return fn(*args, **kwargs)
            finally:
                sys.path = orig
        return closure
    return wrapper
@with_mystery("thing")
def foo():
    from my_module import thing as imp
    imp.thing()
foo()
```

## Answer : it's context manager

Python approach with open files

- Opens and then closes it
