# Record

[index](./README.md)

A **Record** is a group of named values. 

## Creating a simple Record

```coffeescript
thatGirl = { name: "Renée", age: 30 }
```

## Making records from other records
We can construct new records by using another record to use as a starting point, and then specifying only the fields we want to be different.
```coffeescript
original = { birds: 5, zebras: 2, iguanas: 7, goats: 1 }

fromOriginal = { original & birds: 4, iguanas: 3 }
```

> Note that `&` can't introduce new fields to a record, or change the types of existing fields. (Trying to do either of these will result in an error at build time!)

## Optional Record Fields
Roc supports optional record fields using the `?` operator. It is intended for optional config records and therefor destructuring is the only way to implement a record with optional fields:

```coffeescript
table = \{ 
        height, 
        width, 
        title? "oak", 
        description? "a wooden table" 
    }
    -> ...
```

### Reference other expressions in the record destructure
Default values can reference other expressions in the record destructure; if you wanted, you could write

### Optional Record values are no good fit for data modelling

It's impossible to create optional values outside the destructuring pattern. Trying this:

```coffeescript
thatGirl : { name ? Str, surname : Str }
thatGirl = { surname: "not of your business" }
```

Will result in an compile time error:
> Looks like the name field is missing.