## Addon

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
          "type": "number",
          "minimum": 0,
          "exclusiveMinimum": true
        },
        "purchase": {
          "type": "number",
          "minimum": "original",
          "exclusiveMinimum": true
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
          "type": "string",
          "format": "uri"
        },
        "listing": {
          "type": "string",
          "format": "uri"
        },
        "listing_small": {
          "type": "string",
          "format": "uri"
        }
      },
      "required": [
        "bigspot",
        "listing",
        "listing_small"
      ]
    },
    "slug": {
      "type": "string"
    },  
    "route": {
      "type": "string"
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
    "slug",
    "route",
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
