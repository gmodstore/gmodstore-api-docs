## Team

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
    "created_at",
    "updated_at"
  ]
}
```

The `Team` resource is used to represent a team.

### Relations
Name | Type | Description
---- | ---- | -----------
primary_author | [Team User](#resource-types-team-user) | The primary owner of the team
