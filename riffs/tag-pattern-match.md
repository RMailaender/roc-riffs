# Pattern match on Tags

```coffeescript

color = stopligthStr (Yellow 200)

stopligthStr = \stoplightColor -> 
    when stoplightColor is 
        Red _ -> "red"
        Green contrast | Yellow contrast if contrast > 75 -> "not red, but very high contrast"
        Green contrast | Yellow contrast if contrast > 50 -> "not red, but high contrast"
        Green _ | Yellow _ -> "not red"

```