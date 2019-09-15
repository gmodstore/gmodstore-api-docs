# Users

## Main

### Show

```shell
curl "https://api.gmodstore.com/v2/users/76561197988497435" \
  -H "Authorization: Bearer secret"
```

```php
use GmodStore\API\Client;

$client = new Client('secret');

$client->getUser(76561197988497435);
```

> This endpoint requires the `users.read` permission

Fetch a single user.

`GET https://api.gmodstore.com/v2/users/<id>`

**Route parameters:**

Parameter | Type | Description
--------- | ---- | -----------
id | integer | The SteamID64 of the user to fetch

Response code: `200`<br>
Response resource: [User](#resource-types-user)

### Me

```shell
curl "https://api.gmodstore.com/v2/users/me" \
  -H "Authorization: Bearer secret"
```

```php
use GmodStore\API\Client;

$client = new Client('secret');

$client->getUser();
```

> This endpoint only requires a valid API key

Fetches the current user (API Key Owner).

`GET https://api.gmodstore.com/v2/users/me`

Response code: `200`<br>
Response resource: [User](#resource-types-user)
