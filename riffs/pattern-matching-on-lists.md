# Pattern matching on lists

```coffeescript
when myList is
    [] -> 0 # the list is empty
    [Foo, ..] -> 1 # it starts with a Foo tag
    [_, ..] -> 2 # it contains at least one element, which we ignore
    [Foo, Bar, ..] -> 3 # it starts with a Foo tag followed by a Bar tag
    [Foo, Bar, Baz] -> 4 # it has exactly 3 elements: Foo, Bar, and Baz
    [Foo, a, ..] -> 5 # its first element is Foo, and its second we name `a`
    [Ok a, ..] -> 6 # it starts with an Ok containing a payload named `a`
    [.., Foo] -> 7 # it ends with a Foo tag
    [A, B, .., C, D] -> 8 # it has certain elements at the beginning and end
```

--- 

See also:
- [Pattern Matching](../pattern-matching.md)