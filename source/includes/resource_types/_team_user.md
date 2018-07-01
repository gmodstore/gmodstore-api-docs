## Team User

> JSON Schema:

```json
{
  "$schema": "http://json-schema.org/draft-07/schema",
  "type": "object",
  "properties": {
    "team_id": {
      "type": "integer",
      "minimum": 1
    },
    "primary": {
      "type": "boolean"
    }
  },
  "required": [
    "team_id",
    "primary"
  ]
}
```

The `Team User` resource is used to represent a member of a team, it acts as a link between a real [User](#resource-types-user) and a team.

### Relations
Name | Type | Description
---- | ---- | -----------
user | [User](#resource-types-user) | The user this team user represents
