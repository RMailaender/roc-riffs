# Record

[index](./README.md)

A **Record** is a group of named values. 

## Creating a simple Record

```coffeescript
thatGirl = { name: "Renée", age: 30 }
```

## Making records from other records with `&`

```coffeescript
thatGirl = { name: "Renée", age: 30 }

thatOtherGirl = { thatGirl & name: "Alex" }
```

> Note that `&` can't introduce new fields to a record, or change the types of existing fields. (Trying to do either of these will result in an error at build time!)

## Optional Record Fields
Roc supports optional record fields using the `?` operator. It is intended for optional config records and therefor destructuring is the only way to implement a record with optional fields:

```coffeescript
table = \{ 
        height, 
        width, 
        title ? "oak", 
        description ? Str.concat "A table called " title
    }
    -> ...
```

### Optional Record values are no good fit for data modelling

It's impossible to create optional values outside the destructuring pattern. Trying this:

```coffeescript
thatGirl : { name ? Str, surname : Str }
thatGirl = { surname: "not of your business" }
```

Will result in an compile time error:
> Looks like the name field is missing.