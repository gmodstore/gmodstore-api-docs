## User

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
    "avatar": {
      "type": "string",
      "format": "uri"
    },
    "country_code": {
      "type": "string"
    },
    "slug": {
      "type": "string"
    },
    "ban_properties": {
      "type": "array",
      "items": {
        "type": "string",
        "enum": [
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
      }
    }
  },
  "required": [
    "id",
    "name",
    "avatar",
    "slug",
    "ban_properties"
  ]
}
```

The `User` resource is used to represent a user on the site.

<aside class="notice">
  The `country_code` field may be omitted if you don't have permission to view it.
</aside>

### Relations
Name | Type | Description
---- | ---- | -----------
group | [Permission Group](#resource-types-permission-group) | The user's permission group

