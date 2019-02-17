## Permission Group

> JSON Schema:

```json
{
  "$schema": "http://json-schema.org/draft-07/schema",
  "type": "object",
  "properties": {
    "id": {
      "type": "integer",
      "minimum": 1
    },
    "title": {
      "type": "string"
    },
    "display_order": {
      "type": "integer",
      "minimum": 0
    }
  },
  "required": [
    "id",
    "title",
    "display_order"
  ]
}
```

The `Permission Group` resource is used to represent a permission group / rank / role.
