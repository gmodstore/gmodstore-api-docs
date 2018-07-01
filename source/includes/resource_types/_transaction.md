## Transaction

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
    "price": {
      "type": "number",
      "minimum": 0,
      "exclusiveMinimum": true
    },
    "refunded": {
      "type": "boolean"
    }
  },
  "required": [
    "id",
    "price",
    "refunded"
  ]
}
```

The `Transaction` resource is used to represent a transaction.

### Relations
Name | Type | Description
---- | ---- | -----------
user | [User](#resource-types-user) | The user
