## Reviews

### Index

```shell
curl "https://api.gmodstore.com/addons/565/reviews" \
  -H "Authorization: Bearer secret"
```

```php
use GmodStore\API\Client;

$client = new Client('secret');

$client->getAddon(565)->getReviews();
```

> This endpoint requires the `addons.reviews.read` permission

Fetch all the reviews of an addon.

`GET https://api.gmodstore.com/addons/<id>/reviews`

**Route parameters:**

Name | Type | Description
---- | ---- | -----------
id | Integer | The id of the addon to fetch the reviews of

Response code: `200`<br>
Response resource: [Collection](#resource-types-collection)<[Addon Review](#resource-types-addon-review)>


### Show

```shell
curl "https://api.gmodstore.com/addons/565/reviews/223" \
  -H "Authorization: Bearer secret"
```

```php
use GmodStore\API\Client;

$client = new Client('secret');

$client->getAddon(565)->getReview(223);
```

> This endpoint requires the `addons.reviews.read` permission

Fetch a review of an addon.

`GET https://api.gmodstore.com/addons/<addon_id>/reviews/<review_id>`

**Route parameters:**

Name | Type | Description
---- | ---- | -----------
addon_id  | Integer | The id of the addon the review is of
review_id | Integer | The id of the review to fetch

Response code: `200`<br>
Response resource: [Addon Coupon](#resource-types-addon-coupon)
