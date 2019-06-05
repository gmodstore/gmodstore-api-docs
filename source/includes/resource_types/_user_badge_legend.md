## User Badge Legend

> JSON Schema:

```json
{
  "$schema": "http://json-schema.org/draft-07/schema",
  "type": "object",
  "properties": {
    "id": {
      "type": "string"
    },
    "name": {
      "type": "string"
    },
    "description": {
      "type": "string"
    },
    "ext": {
      "type": "string"
    }
  },
  "required": [
    "id",
    "name",
    "description"
  ]
}
```

The `User Badge Legend` resource is used to represent a the parent of a User Badge, which also contains far more info than a User Badge.
