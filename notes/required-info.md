When generating a schema from a type, we generally have all of the information we need.  (I'm having trouble thinking of a type declaration that doesn't have enough information to define a schema.)

However, code generation sometimes requires some annotative keywords.  For example,

```json
{
  "type": "object",
  "properties": {
    "foo": { "type": "integer" },
    "bar": { "type": "string" }
  }
}
```

provides enough information to describe the structure of a type, but a type usually needs a name.

Some types don't need this, though.  For an array of objects,

```jsonc
{
  "type": "array",
  "items": { /* ... */ }
}
```

most languages have one or more built-in collection types that can handle this, e.g. `List<T>` in .Net or `NSArray` in Objective-C, or even a simple array (which probably every usable language has).

For custom objects, though, in order to generate type code correctly, there should be a minimum amount of information present.  Specifically,

- `title` should hold the type name
- `description` could map to a comment or other in-code documentation about the type
- any other ideas?

We also need to identify when these should be required.  Can that be represented in a meta-schema, or will that be up to the generator to decide?