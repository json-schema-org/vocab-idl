# Naming conventions
Because JSON Schema don't have any restrictions on what you can define as property names, therefore you might end up encountering values that are not compliant with the output language.

1. Property names and data model names cannot contain a number as the first character
```json
{"properties": {"12Prop": {}}
```
2. Properties and constants cannot be the same as the model name
```json
{"name": "SomeName", "properties": {"SomeName": {}}
```
3. Properties cannot be reserved keywords
```json
{"name": "return", "properties": {"return": {}}
```
4. Names cannot contain special characters
```json
{"properties": {"some prop !\"#€%&/()=": {}}
```

# Solutions
Depending on what you want to achieve, there is a different solution to the problem.

## Restricting naming format
By restricting what values can be represented as properties, constant and model names you can limit the number of encounters with non-compliant values.

For example, enforcing the following regex `/^[a-z]([a-z][0-9]_)+$/` to make values always follow `lowercase012_3`. 

## Allowing everything
If you allow any values to be present, we must figure out how to handle the specific encounters of values that are non-compliant with the output language.

### Numbers as first characters
```json
{"properties": {"12Prop": {}}
```

- Replace the number with the spelled-out version i.e. the name `12Prop` becomes `TwelveProp`. Must enforce [altered names already exist](#altered-names-already-exist).
- Pre- or append something to the name i.e. `12Prop` becomes `reserved12Prop`. Must enforce [altered names already exist](#altered-names-already-exist).
- Throw an error.


### Properties and constants cannot be the same as the model name

```json
{"name": "SomeName", "properties": {"SomeName": {}}
```

- Pre- or append something to the property i.e. `"properties": {"SomeName": {}}` becomes `"properties": {"reservedSomeName": {}}`. Must enforce [altered names already exist](#altered-names-already-exist).
- Pre- or append something to the model name i.e. `"name": "SomeName"` becomes `"name": "reservedSomeName"`. Must enforce [altered names already exist](#altered-names-already-exist).

### Names cannot be reserved keywords
Please see [handling reserved keywords](./handling%20reserved%20keywords.md) for further details.

### Names cannot contain special characters

- Replace the special character with the spelled-out version i.e. the name `$Prop` becomes `dollarProp`. Must enforce [altered names already exist](#altered-names-already-exist).
List of potential alternatives:
```
' ' -> 'space' 
'!' -> 'exclamation' 
'"' -> 'quotation' 
'#' -> 'hash' 
'$' -> 'dollar' 
'%' -> 'percent' 
'&' -> 'ampersand' 
'\'' -> 'apostrophe' 
'(' -> 'roundleft' 
')' -> 'roundright' 
'*' -> 'asterisk' 
'+' -> 'plus' 
',' -> 'comma' 
'-' -> 'minus' 
'.' -> 'dot' 
'/' -> 'slash' 
':' -> 'colon' 
';' -> 'semicolon' 
'<' -> 'less' 
'=' -> 'equal' 
'>' -> 'greater' 
'?' -> 'question' 
'@' -> 'at' 
'[' -> 'squareleft' 
'\' -> 'backslash' 
']' -> 'squareright' 
'^' -> 'circumflex' 
'_' -> 'underscore' 
'`' -> 'graveaccent' 
'{' -> 'curlyleft' 
'|' -> 'vertical' 
'}' -> 'curlyright' 
'~' -> 'tilde' 
```
- Remove the character completely, i.e. the name `$Prop` becomes `Prop`. Must enforce [altered names already exist](#altered-names-already-exist).

### Altered names already exist
If you decided to go with a solution that alters the name in any way, you must always ensure that it did not collide with already existing names. 