# Teams

## Main

### Show

```shell
curl "https://gmodstore.com/api/v2/teams/177" \
  -H "Authorization: Bearer secret"
```

```php
use GmodStore\API\Client;

$client = new Client('secret');

$client->getTeam(177);
```

> This endpoint requires the `teams.read` permission

Fetch a single team.

`GET https://gmodstore.com/api/v2/teams/<id>`

**Route parameters:**

Name | Type | Description
---- | ---- | -----------
id | integer | The id of the team to fetch

Response code: `200`<br>
Response resource: [Team](#resource-types-team)
