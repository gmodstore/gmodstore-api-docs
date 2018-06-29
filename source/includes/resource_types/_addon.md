## Addon

> JSON Schema:

```json
{
  "$schema": "http://json-schema.org/draft-07/schema",
  "type": "object",
  "properties": {
    "id": {
      "type": "integer"
    },
    "active": {
      "type": "boolean"
    },
    "name": {
      "type": "string"
    },
    "short_description": {
      "type": "string"
    },
    "description": {
      "type": "string"
    },
    "requirements": {
      "type": "array",
      "items": {
        "type": "string"
      }
    },
    "price": {
      "type": "object",
      "properties": {
        "original": {
          "type": "number"
        },
        "purchase": {
          "type": "number"
        }
      },
      "required": [
        "original",
        "purchase"
      ]
    },
    "images": {
      "type": "object",
      "properties": {
        "bigspot": {
          "type": "string"
        },
        "listing": {
          "type": "string"
        },
        "listing_small": {
          "type": "string"
        }
      },
      "required": [
        "bigspot",
        "listing",
        "listing_small"
      ]
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
    "active",
    "name",
    "short_description",
    "description",
    "requirements",
    "price",
    "images",
    "created_at",
    "updated_at"
  ]
}
```

The `Addon` resource is used to represent an addon.

### Relations
Name | Type | Description
---- | ---- | -----------
latest_version | [Addon Version](#resource-types-resource-types-addon-version) | The latest version of the addon
team           | [Team](#resource-types-resource-types-team)                   | The team that owns the addon
