## Bans

### Index

```shell
curl "https://api.gmodstore.com/v2/users/76561197988497435/bans" \
  -H "Authorization: Bearer secret"
```

```php
use GmodStore\API\Client;

$client = new Client('secret');

$client->getUser(76561197988497435)->getBans();
```

> This endpoint requires the `users.read` permission

Fetch all active bans associated with this user.

`GET https://api.gmodstore.com/v2/users/<id>/bans`

**Route parameters:**

Name | Type | Description
---- | ---- | -----------
id | Integer | The SteamID of the user to fetch the bans of

Response code: `200`<br>
Response resource: [Collection](#resource-types-collection)<[Ban](#resource-types-ban)>
