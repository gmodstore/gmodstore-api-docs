## Teams

### Index

```shell
curl "https://api.gmodstore.com/users/76561197988497435/teams" \
  -H "Authorization: Bearer secret"
```

```php
use GmodStore\API\Client;

$client = new Client('secret');

$client->getUser(76561197988497435)->getTeams();
```

> This endpoint requires the `users.read` **AND** `teams.read` permissions

Fetch all the teams of a user.

`GET https://api.gmodstore.com/users/<id>/teams`

**Route parameters:**

Name | Type | Description
---- | ---- | -----------
id | Integer | The SteamID of the user to fetch the team of

Response code: `200`<br>
Response resource: [Team](#resource-types-team)
