# Lists that hold elements of different types

```coffee
List.map [StrElem "A", StrElem "b", NumElem 1, StrElem "c", NumElem -3] \elem ->
    when elem is
        NumElem num -> Num.isNegative num
        StrElem str -> Str.isCapitalized str
# returns [Bool.true, Bool.false, Bool.false, Bool.false, Bool.true]
```

---

See also:
- [Lists](../lists.md)
- [Pattern Matching on Lists](./pattern-matching-on-lists.md)