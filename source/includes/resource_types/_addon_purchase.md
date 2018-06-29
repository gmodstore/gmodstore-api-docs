## Addon Purchase

> JSON Schema:

```json
{
  "$schema": "http://json-schema.org/draft-07/schema",
  "type": "object",
  "properties": {
    "revoked": {
      "type": "boolean"
    },
    "created_at": {
      "type": "string",
      "format": "date-time"
    },
    "updated_at": {
      "type": "string",
      "format": "date-time"
    }
  },
  "required": [
    "revoked",
    "created_at",
    "updated_at"
  ]
}
```

The `Addon Purchase` resource is used to represent *ownership* of an addon.

### Relations
Name | Type | Description
---- | ---- | -----------
addon       | [Addon](#resource-types-addon)             | The addon the "purchase" is of
transaction | [Transaction](#resource-types-transaction) | The transaction (null if the "purchase" was granted)
user        | [User](#resource-types-team-user)          | The user that the "purchase" belongs to
