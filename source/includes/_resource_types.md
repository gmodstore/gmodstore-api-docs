# Resource Types
Resources are always returned from the API in the format to the right (JSON Schema)

```json
{
  "$schema": "http://json-schema.org/draft-07/schema",
  "type": "object",
  "properties": {
    "data": {
      "type": ["array", "object"]
    }
  }
}
```

Some resources have an "Relations" section, these relations can be retrieved by using the `with` query parameter;
for example, to retrieve the `user` relation one could append `?with=user` to the resources URL, this is done to save bandwidth.
To retrieve multiple relations simply pass a comma delimited list of names, e.g `?with=user,transaction` would retrieve 
both the `user` and `transaction` relationships of the given resource (provided it had those relations).
The relations will be appended to the resource with a key matching matching their name(s).

Finally you should be aware that all JSON Schemas are represented as JSON Schema.

## Collection

> JSON Schema:

```json
{
    "$schema": "http://json-schema.org/draft-07/schema",
    "type": "array",
    "items": {
      "type": "object"
    }
}
```

A generic collection of resources, most resources use this collection type but some may have special ones.
In this type of collection *all* resource properties are maintained and they are placed in an array.

<aside class="notice">
  This is a special resource type!
</aside>




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
      }
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
      }
    },
    "created_at": {
      "type": "string",
      "format": "date-time"
    },
    "updated_at": {
      "type": "string",
      "format": "date-time"
    }
  }
}
```

The `Addon` resource is used to represent an addon.

### Relations
Name | Type | Description
---- | ---- | -----------
latest_version | [Addon Version](#resource-types-resource-types-addon-version) | The latest version of the addon
team           | [Team](#resource-types-resource-types-team)                   | The team that owns the addon





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
  }
}
```

The `Addon Coupon` resource is used to represent a coupon for an addon

### Relations
Name | Type | Description
---- | ---- | -----------
addon | [Addon](#resource-types-resource-types-addon) | The addon the coupon can be used with




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
  }
}
```

The `Addon Media` resource is used to represent a media object belonging to an addon.

### Relations
Name | Type | Description
---- | ---- | -----------
addon | [Addon](#resource-types-addon) | The addon the media is for




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
  }
}
```

The `Addon Review` resource is used to represent a review of an addon.

### Relations
Name | Type | Description
---- | ---- | -----------
addon  | [Addon](#resource-types-addon) | The addon the review is for
author | [User](#resource-types-user)   | The author of the review




## Addon Version

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
    "changelog": {
      "type": "string"
    },
    "file_hash": {
      "type": "string"
    },
    "file_size": {
      "type": "integer"
    },
    "created_at": {
      "type": "string",
       "format": "date-time"
    },
    "updated_at": {
      "type": "string",
      "format": "date-time"
    }
  }
}
```

The `Addon Version` resource is used to represent a specific version of an addon.

### Relations
Name | Type | Description
---- | ---- | -----------
addon | [Addon](#resource-types-addon) | The addon the version is of




## Addon Purchase

> JSON Schema:

```json
{
  "$schema": "http://json-schema.org/draft-07/schema",
  "type": "object",
  "properties": {
    "revoked": {
      "type": "boolean"
    },
    "created_at": {
      "type": "string",
      "format": "date-time"
    },
    "updated_at": {
      "type": "string",
      "format": "date-time"
    }
  }
}
```

The `Addon Purchase` resource is used to represent *ownership* of an addon.

### Relations
Name | Type | Description
---- | ---- | -----------
addon       | [Addon](#resource-types-addon)             | The addon the "purchase" is of
transaction | [Transaction](#resource-types-transaction) | The transaction (null if the "purchase" was granted)
user        | [User](#resource-types-team-user)          | The user that the "purchase" belongs to




## Permission Group

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
    }
  }
}
```

The `Permission Group` resource is used to represent a permission group / rank / role.




## Team

> JSON Schema:

```json
{
  "$schema": "http://json-schema.org/draft-07/schema",
  "type": "object",
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
}
```

The `Team` resource is used to represent a team.

### Relations
Name | Type | Description
---- | ---- | -----------
primary_author | [Team User](#resource-types-team-user) | The primary owner of the team




## Team User

> JSON Schema:

```json
{
  "$schema": "http://json-schema.org/draft-07/schema",
  "type": "object",
  "team_id": {
    "type": "integer"
  },
  "primary": {
    "type": "boolean"
  }
}
```

The `Team User` resource is used to represent a member of a team, it acts as a link between a real [User](#resource-types-user) and a team.

### Relations
Name | Type | Description
---- | ---- | -----------
user | [User](#resource-types-user) | The user this team user represents




## Transaction

> JSON Schema:

```json
{
  "$schema": "http://json-schema.org/draft-07/schema",
  "type": "object",
  "id": {
    "type": "integer"
  },
  "price": {
    "type": "number"
  },
  "refunded": {
    "type": "boolean"
  }
}
```

The `Transaction` resource is used to represent a transaction.

### Relations
Name | Type | Description
---- | ---- | -----------
user | [User](#resource-types-user) | The user




## User

> JSON Schema:

```json
{
  "$schema": "http://json-schema.org/draft-07/schema",
  "type": "object",
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
}
```

The `User` resource is used to represent a user on the site.
