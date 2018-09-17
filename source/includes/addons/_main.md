# Addons

## Main

### Index

```shell
curl "https://api.gmodstore.com/v2/addons" \
  -H "Authorization: Bearer secret"
```

```php
use GmodStore\API\Client;

$client = new Client('secret');

$client->getAddons();
```

> This endpoint requires the `addons.read` permission

Fetch all the addons that you have access to.

`GET https://api.gmodstore.com/v2/addons`

Response code: `200`<br>
Response resource: [Collection](#resource-types-collection)<[Addon](#resource-types-addon)>


### Show

```shell
curl "https://api.gmodstore.com/v2/addons/565" \
  -H "Authorization: Bearer secret"
```

```php
use GmodStore\API\Client;

$client = new Client('secret');

$client->getAddon(565);
```

> This endpoint requires the `addons.read` permission

Fetch a single addon.

`GET https://api.gmodstore.com/v2/addons/<id>`

**Route parameters:**

Parameter | Type | Description
--------- | ---- | -----------
id | integer | The id of the addon to fetch

Response code: `200`<br>
Response resource: [Addon](#resource-types-addon)

