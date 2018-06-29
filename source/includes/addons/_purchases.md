## Purchases

### Index

```shell
curl "https://api.gmodstore.com/addons/565/purchases" \
  -H "Authorization: Bearer secret"
```

```php
use GmodStore\API\Client;

$client = new Client('secret');

$client->getAddon(565)->getPurchases();
```

> This endpoint requires the `addons.purchases.read` permission

Fetch all purchases of an addon.

`GET https://gmodstore.com/addons/<id>/purchases`

**Route parameters:**

Name | Type | Description
---- | ---- | -----------
id | Integer | The id of the addon to fetch the purchases of

Response code: `200`<br>
Response resource: [Collection](#resource-types-collection)<[Addon Purchase](#resource-types-addon-purchase)>


### Store

```shell
curl -X POST "https://api.gmodstore.com/addons/565/purchases" \
  -H "Authorization: Bearer secret" \
  -d "user_id=76561198127820866"
```

```php
use GmodStore\API\Client;

$client = new Client('secret');

$client->getAddon(565)->addPurchase(76561198127820866);
```

> This endpoint requires the `addons.purchases.write` permission

Create a purchase for an addon.

`POST https://gmodstore.com/addons/<id>/purchases`

**Route parameters:**

Name | Type | Description
---- | ---- | -----------
id | Integer | The id of the addon to create the purchase for

**Form fields:**

Name | Type | Description
---- | ---- | -----------
user_id | Integer | The id of the user to create the purchase for


Response code: `201`<br>
Response resource: [Addon Purchase](#resource-types-addon-purchase)


### Show

```shell
curl "https://api.gmodstore.com/addons/565/purchases/76561198091472117" \
  -H "Authorization: Bearer secret"
```

```php
use GmodStore\API\Client;

$client = new Client('secret');

$client->getAddon(565)->getPurchase(76561198091472117);
```

> This endpoint requires the `addons.purchases.read` permission

Get a purchase of an addon (by user).

`GET https://gmodstore.com/addons/<addon_id>/purchases/<user_id>`

**Route parameters:**

Name | Type | Description
---- | ---- | -----------
addon_id | Integer | The id of the addon the purchase belongs to
user_id  | Integer | The id of the user who made the purchase

Response code: `200`<br>
Response resource: [Addon Purchase](#resource-types-addon-purchase)


### Update

```shell
curl -X POST "https://api.gmodstore.com/addons/565/purchases/76561198091472117" \
  -H "Authorization: Bearer secret" \
  -d "revoked=1"
```

```php
use GmodStore\API\Client;

$client = new Client('secret');

$client->getAddon(565)->getPurchase(76561198127820866)->update([
  'revoked' => true
]);
```

> This endpoint requires the `addons.purchases.write` permission

Create a purchase for an addon.

`POST https://gmodstore.com/addons/<id>/purchases`

**Route parameters:**

Name | Type | Description
---- | ---- | -----------
id | Integer | The id of the addon to create the purchase for

**Form fields:**

Name | Type | Description
---- | ---- | -----------
revoked | Boolean | Whether or not the purchase is revoked

Response code: `201`<br>
Response resource: [Addon Purchase](#resource-types-addon-purchase)

