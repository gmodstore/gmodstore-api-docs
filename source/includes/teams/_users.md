## Users

### Index

```shell
curl "https://api.gmodstore.com/v2/teams/177/users" \
  -H "Authorization: Bearer secret"
```

```php
use GmodStore\API\Client;

$client = new Client('secret');

$client->getTeam(177)->getUsers();
```

> This endpoint requires the `teams.read` **AND** `users.read` permissions

Fetch all the users in the given team.

`GET https://api.gmodstore.com/v2/teams/<id>/users`

**Route parameters:**

Name | Type | Description
---- | ---- | -----------
id | integer | The id of the team to fetch

Response code: `200`<br>
Response resource: [Collection](#resource-types-collection)<[Team User](#resource-types-team-user)>
