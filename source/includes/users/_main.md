# Users

## Main

### Show

```shell
curl "https://gmodstore.com/api/v2/users/76561197988497435" \
  -H "Authorization: Bearer secret"
```

```php
use GmodStore\API\Client;

$client = new Client('secret');

$client->getUser(76561197988497435);
```

> This endpoint requires the `users.read` permission

Fetch a single user.

`GET https://gmodstore.com/api/v2/users/<id>`

**Route parameters:**

Parameter | Type | Description
--------- | ---- | -----------
id | integer | The SteamID64 of the user to fetch

Response code: `200`<br>
Response resource: [User](#resource-types-user)
