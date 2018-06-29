## Addon Media

> JSON Schema:

```json
{
  "$schema": "http://json-schema.org/draft-07/schema",
  "type": "object",
  "properties": {
    "id": {
      "type": "string"
    },
    "type": {
      "type": "string"
    },
    "title": {
      "type": "string"
    }
  },
  "required": [
    "id",
    "type",
    "title"
  ]
}
```

The `Addon Media` resource is used to represent a media object belonging to an addon.

### Relations
Name | Type | Description
---- | ---- | -----------
addon | [Addon](#resource-types-addon) | The addon the media is for
