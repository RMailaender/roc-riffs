# List.walk

> `reduce`, `fold`

```coffee
List.walk [1, 2, 3, 4, 5] { evens: [], odds: [] } \state, elem ->
    if Num.isEven elem then
        { state & evens: List.append state.evens elem }
    else
        { state & odds: List.append state.odds elem }

# returns { evens: [2, 4], odds: [1, 3, 5] }
```

See also:
- [Lists](../lists.md)