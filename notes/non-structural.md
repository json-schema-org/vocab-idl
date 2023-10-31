For non-structural details, many languages support (either through built-in mechanisms or third-party libraries) some way to annotate a type to indicate what range of values are valid for an object's members.  In JSON Schema, these are represented with keywords like

- `minimum`
- `maxLength`
- `multipleOf`
- `uniqueItems`
- etc.

However, the way to represent these in language code varies greatly.

Translating these requirements to the language model allows validation logic that's already in the language to be invoked.  However it also promotes using that validation logic (which may differ from JSON Schema's intent) over using JSON Schema directly.  This may cause disparity between the validations from the language and JSON Schema.

Unless we can ensure that the code annotations provide the same validation that an equivalent JSON Schema would, I'm not convinced including them is a good idea.

---

Another aspect of this is schemas which have these requirements at the top-level:

```jsonc
{
  "type": "array",
  "items": { /* ... */ },
  "minItems": 4
}
```

Usually these types of constraints are expressed on object members, not on types.  Does it make sense to say that an instance of a array must have at least 4 items, or that a lone integer must be more than 50?  (I can see a case for `minimum: 0` being used to identify an unsigned integer type, though.)