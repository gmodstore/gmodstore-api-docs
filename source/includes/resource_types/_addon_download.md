## Addon Download

> JSON Schema:

```json
{
  "$schema": "http://json-schema.org/draft-07/schema",
  "type": "object",
  "properties": {
    "url": {
      "type": "string",
      "format": "uri"
    }
  },
  "required": [
    "url"
  ]
}
```

The `Addon Download` resource is used as a container for a url which points to the
[Download Server](#), when a `GET` request is sent to the url the download server will serve the addon file.<br>

**NOTE:** The url is valid for 24 hours **ONLY**!
