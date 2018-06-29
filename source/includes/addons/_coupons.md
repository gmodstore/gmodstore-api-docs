## Coupons

### Index

```shell
curl "https://gmodstore.com/api/v2/addons/565/coupons" \
  -H "Authorization: Bearer secret"
```

```php
use GmodStore\API\Client;

$client = new Client('secret');

$client->getAddon(565)->getCoupons();
```

> This endpoint requires the `addons.coupons.read` permission

Fetch all the coupons for an addon.

`GET https://gmodstore.com/api/v2/addons/<id>/coupons`

**Route parameters:**

Name | Type | Description
---- | ---- | -----------
id | Integer | The id of the addon to fetch the coupons of

Response code: `200`<br>
Response resource: [Collection](#resource-types-collection)<[Addon Coupon](#resource-types-addon-coupon)>


### Store

```shell
curl -X POST "https://gmodstore.com/addons/565/coupons" \
  -H "Authorization: Bearer secret" \
  -d "percent=25&code=25OFF&max_uses=10&expires_at=25.12.2025"
```

```php
use GmodStore\API\Client;

$client = new Client('secret');

$client->getAddon(565)->createCoupon([
  'percent' => 25,
  'code' => '25OFF',
  'max_uses' => 10,
  'expires_at' => '25.12.2025'
]);
```

> This endpoint requires the `addons.coupons.write` permission

Create an addon coupon.

`POST https://gmodstore.com/api/v2/addons/<id>/coupons`

**Route parameters:**

Name | Type | Description
---- | ---- | -----------
id | Integer | The id of the addon to create the coupon for

**Form fields:**

Name | Type | Description
---- | ---- | -----------
percent    | Integer      | The percentage discount
code       | String       | The code for the coupon
max_uses   | Integer      | The maximum number of uses for
expires_at | Date (d.m.Y) | The expiry date (`null` for infinite)

Response code: `201`<br>
Response resource: [Addon Coupon](#resource-types-addon-coupon)


### Show

```shell
curl "https://gmodstore.com/api/v2/addons/565/coupons/967" \
  -H "Authorization: Bearer secret"
```

```php
use GmodStore\API\Client;

$client = new Client('secret');

$client->getAddon(565)->getCoupon(967);
```

> This endpoint requires the `addons.coupons.read` permission

Fetch an addon's coupon.

`GET https://gmodstore.com/api/v2/addons/<addon_id>/coupons/<coupon_id>`

**Route parameters:**

Name | Type | Description
---- | ---- | -----------
addon_id  | Integer | The id of the addon the coupon belongs to
coupon_id | Integer | The id of the coupon to fetch

Response code: `200`<br>
Response resource: [Addon Coupon](#resource-types-addon-coupon)


### Update

```shell
curl -X PUT "https://gmodstore.com/addons/565/coupons/967" \
  -H "Authorization: Bearer secret" \
  -d "percent=75&code=75OFF&max_uses=10&expires_at=25.12.2025"
```

```php
use GmodStore\API\Client;

$client = new Client('secret');

$client->getAddon(565)->getCoupon(967)->update([
  'percent' => 75,
  'code' => '75OFF'
]);
```

> This endpoint requires the `addons.coupons.write` permission

Update an addon's coupon.

`PUT https://gmodstore.com/api/v2/addons/<addon_id>/coupons/<coupon_id>`

**Route parameters:**

Name | Type | Description
---- | ---- | -----------
addon_id  | Integer | The id of the addon the coupon belongs to
coupon_id | Integer | The id of the coupon to update

**Form fields:**

Name | Type | Description
---- | ---- | -----------
percent    | Integer      | The percentage discount
code       | String       | The code for the coupon
max_uses   | Integer      | The maximum number of uses for
expires_at | Date (d.m.Y) | The expiry date (`null` for infinite)

Response code: `200`<br>
Response resource: [Addon Coupon](#resource-types-addon-coupon)


### Destroy

```shell
curl -X DELETE "https://gmodstore.com/api/v2/addons/565/coupons/967" \
  -H "Authorization: Bearer secret"
```

```php
use GmodStore\API\Client;

$client = new Client('secret');

$client->getAddon(565)->getCoupon(967)->delete();
```

> This endpoint requires the `addons.coupons.write` permission

Destroy an addon's coupon.

`DELETE https://gmodstore.com/api/v2/addons/<addon_id>/coupons/<coupon_id>`

**Route parameters:**

Name | Type | Description
---- | ---- | -----------
addon_id  | Integer | The id of the addon the coupon belongs to
coupon_id | Integer | The id of the coupon to destroy

Response code: `204`
