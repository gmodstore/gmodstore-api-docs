## Addon Review

> JSON Schema:

```json
{
  "$schema": "http://json-schema.org/draft-07/schema",
  "type": "object",
  "properties": {
    "id": {
      "type": "integer"
    },
    "title": {
      "type": "string"
    },
    "version": {
      "type": "string"
    },
    "body": {
      "type": "string"
    },
    "rating": {
      "type": "number"
    }
  },
  "required": [
    "id",
    "title",
    "version",
    "body",
    "rating"
  ]
}
```

The `Addon Review` resource is used to represent a review of an addon.

### Relations
Name | Type | Description
---- | ---- | -----------
addon  | [Addon](#resource-types-addon) | The addon the review is for
author | [User](#resource-types-user)   | The author of the review
