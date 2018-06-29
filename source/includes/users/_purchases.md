## Purchases

### Index

```shell
curl "https://gmodstore.com/api/v2/users/76561197988497435/purchases" \
  -H "Authorization: Bearer secret"
```

```php
use GmodStore\API\Client;

$client = new Client('secret');

$client->getUser(76561197988497435)->getPurchases();
```

> This endpoint requires the `users.read` **AND** `addons.purchases.read` permissions

Fetch all purchases a user has made.

`GET https://gmodstore.com/api/v2/users/<id>/purchases`

**Route parameters:**

Parameter | Type | Description
--------- | ---- | -----------
id | Integer | The SteamID of the user to fetch the purchases of

Response code: `200`<br>
Response resource: [Collection](#resource-types-collection)<[Addon Purchase](#resource-types-addon-purchase)>
