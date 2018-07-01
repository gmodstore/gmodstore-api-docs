## Addon Version

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
    "name": {
      "type": "string"
    },
    "changelog": {
      "type": "string"
    },
    "file_hash": {
      "type": "string"
    },
    "file_size": {
      "type": "integer",
      "minimum": 0
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
    "id",
    "name",
    "changelog",
    "file_hash",
    "file_size",
    "created_at",
    "updated_at"
  ]
}
```

The `Addon Version` resource is used to represent a specific version of an addon.

### Relations
Name | Type | Description
---- | ---- | -----------
addon | [Addon](#resource-types-addon) | The addon the version is of
