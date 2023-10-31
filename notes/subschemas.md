Subschemas and nested types appear everywhere.  Generally, a subschema will represent a new type.

```json
{
  "type": "object",
  "properties": {
    "foo": { "type": "integer" },
    "bar": {
      "type": "object",
      "properties": {
        "numbers": {
          "type": "array",
          "items": { "type": "number" }
        }
      }
    }
  }
}
```

For this schema, we have four types being represented:

- the top-level object, with properties `foo` and `bar`
- an integer
- an object at `/properties/bar`
- a number

(#45 discusses built-in types, so we'll leave that out of this issue.)

Specifically, we need to focus on the two custom objects: the top-level and whatever `bar` is.

I would expect a generator to create two types from this schema.  Are there any restrictions that people can see?

---

What happens when a subschema is duplicated?

```json
{
  "type": "object",
  "properties": {
    "foo": { "type": "integer" },
    "bar": {
      "type": "object",
      "properties": {
        "numbers": {
          "type": "array",
          "items": { "type": "number" }
        }
      }
    },
    "baz": {
      "type": "object",
      "properties": {
        "numbers": {
          "type": "array",
          "items": { "type": "number" }
        }
      }
    }
  }
}
```

Here, `/properties/bar` and `/properties/baz` are identical.  Is this the author's intent, or are these two semantically (business rules) different yet functionally (shape/structure) identical?  Do we need a way to discern this?  Maybe #50 can help identify author intent.  For example, tf the subschemas have the same `title`, it was intended that they're the same type.

(`$ref`'d subschemas are obviously the same type.)