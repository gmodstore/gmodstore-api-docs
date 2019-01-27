## Ban

> JSON Schema:

```json
{
  "$schema": "http://json-schema.org/draft-07/schema",
  "type": "object",
  "properties": {
    "user_id": {
      "type": "string"
    },
    "reason": {
      "type": "string"
    },
    "unban_reason": {
      "type": "string"
    },
    "properties": {
      "type": "array",
      "items": [
        "everything",
        "addon.create",
        "addon.purchase",
        "addon.download",
        "addon.review",
        "addon.comment",
        "job.create",
        "job.apply",
        "job.review",
        "job.comment",
        "ban.appeal"
      ]
    },
    "start": {
      "type": "string",
      "format": "date-time"
    },
    "end": {
      "type": "string",
      "format": "date-time"
    }
  },
  "required": [
    "user_id",
    "reason",
    "unban_reason",
    "properties",
    "start",
    "end"
  ]
}
```

The `Ban` resource is used to represent a user ban on the site.