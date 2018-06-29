## Addon Coupon

> JSON Schema:

```json
{
  "$schema": "http://json-schema.org/draft-07/schema",
  "type": "object",
  "properties": {
    "id": {
      "type": "integer"
    },
    "code": {
      "type": "string"
    },
    "percent": {
      "type": "number"
    },
    "max_uses": {
      "type": "integer"
    },
    "expires_at": {
      "type": "string",
      "format": "date-time"
    },
    "created_at": {
      "type": "string",
      "format": "date-time"
    },
    "updated_at": {
      "type": "integer",
      "format": "date-time"
    }
  },
  "required": [
    "id",
    "code",
    "percent",
    "max_uses",
    "expires_at",
    "created_at",
    "updated_at"
  ]
}
```

The `Addon Coupon` resource is used to represent a coupon for an addon

### Relations
Name | Type | Description
---- | ---- | -----------
addon | [Addon](#resource-types-resource-types-addon) | The addon the coupon can be used with
