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
  },
  "required": [
    "data"
  ]
}
```

Some resources have an "Relations" section, these relations can be retrieved by using the `with` query parameter;
for example, to retrieve the `user` relation one could append `?with=user` to the resources URL, this is done to save bandwidth.
To retrieve multiple relations simply pass a comma delimited list of names, e.g `?with=user,transaction` would retrieve 
both the `user` and `transaction` relationships of the given resource (provided it had those relations). 

The relations will be appended to the resource with a key matching matching their name(s).

Finally you should be aware that all JSON Schemas are represented as JSON Schema.

<aside class="notice">
One thing to note is that you are not able to return relations that have multiple items, 
for instance you will not be able to return all purchases of an addon through the addon's show API.
</aside>


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
