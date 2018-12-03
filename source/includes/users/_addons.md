## Addons

### Index

```shell
curl "https://api.gmodstore.com/v2/users/76561197988497435/addons" \
  -H "Authorization: Bearer secret"
```

```php
use GmodStore\API\Client;

$client = new Client('secret');

$client->getUser(76561197988497435)->getAddons();
```

> This endpoint requires the `users.read` **AND** `addons.read` permissions

Fetch all the addons authored / co-authored by a user.

`GET https://api.gmodstore.com/v2/users/<id>/addons`

**Route parameters:**

Name | Type | Description
---- | ---- | -----------
id | Integer | The SteamID of the user to fetch the addons of

Response code: `200`<br>
Response resource: [Collection](#resource-types-collection)<[Addon](#resource-types-addon)>
