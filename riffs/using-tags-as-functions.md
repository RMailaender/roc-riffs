# Using tags as functions

Let's say I want to apply a tag to a bunch of elements in a list. For example:

```coffee
List.map ["a", "b", "c"] \str -> Foo str
```

This is a perfectly reasonable way to write it, but I can also write it like this:

```coffee
List.map ["a", "b", "c"] Foo
``` 
These two versions compile to the same thing. As a convenience, Roc lets you specify a tag name where a function is expected; when you do this, the compiler infers that you want a function which uses all of its arguments as the payload to the given tag.

---

See also:
- [Lists](../lists.md)
- [Tags](../tags.md)