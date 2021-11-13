# Has type Assertion

We use the very same types as JSON Schema allows, which each has a variant in each respective language.

If multiple arguments are are provided such as below, it means that the argument above the other is used as a generic input.
```json
{
    "assertion": "hasType",
    "arguments": [
        "array",
        "string"
    ]
}
```
In the example above it means that we have an array of strings. Restriction to this syntax is only one generic input allowed per type.


| Type | TS | Java |
| ----------- | ----------- | ----------- |
| number | number | double
| string | string | String
| boolean | boolean | boolean
| null | null | `JsonNull.getInstance()`
| object | any | Object
| array< Type > | < Type >[] | List< Type >


## Null restrictions

`null` will in many cases require a custom wrapper class to represent a null value. I.e. for Java we recommend `JsonNull`:

```java
class JsonNull {
    static public JsonNull getInstance() {
        return null;
    }
}
```

In others, such as `TS` we can use `null`.