## User

> JSON Schema:

```json
{
  "$schema": "http://json-schema.org/draft-07/schema",
  "type": "object",
  "properties": {
    "id": {
      "type": "integer"
    },
    "name": {
      "type": "string"
    },
    "avatar": {
      "type": "string",
      "format": "uri"
    },
    "country_code": {
      "type": "string"
    }
  },
  "required": [
    "id",
    "name",
    "avatar",
    "country_code"
  ]
}
```

The `User` resource is used to represent a user on the site.
