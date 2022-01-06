# Handling reserved keywords

JSON Schema have no restrictions on property names. However in programming languages, there often is reserved keywords that properties cannot be named.

For example given the following JSON Schema:

```json
{
  "$schema": "https://json-schema.org/draft/2020-12/idl-schema",
  "name": "SomeTitle",
  "type": "object",
  "properties": {
    "return": {
      "type": "string"
    }
  }
}
```

The optimal output to something like TypeScript, would probably be the following:

```ts
class SomeTitle {
   return: string;
}
```

However, TypeScript don't allow such a property name, because it collide with the reserved keyword `return` used to return data from functions.

## Solutions
There are no specific solutions that we enforce, it is up to the implementor.

To make your life easier, here is the list of keywords that are reserved: 
- [TypeScript](reserved%20keywords/typescript.md)
- [C#](reserved%20keywords/csharp.md)
- [javascript](reserved%20keywords/javascript.md)
- [java](reserved%20keywords/java.md)

If the reserved keyword list your are looking for is not present, please provide a PR!

### Adding something extra to the property name
One of the solutions is to pre- or post-fix some kind of word to the rendered property name. 

For example prefixing `reserved` to a property name.

```ts
class SomeTitle {
   reservedReturn: string;
}
```

This means you will end up with two names for the property. The one rendered, and the one needed for serializing the data model (because otherwise validating the serialized data wont validate correctly against the JSON Schema).

### Throw an error
The easiest solution is to throw an error whenever they are encountered, and stopping the generation of models. 