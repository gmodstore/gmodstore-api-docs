## Badges

### Index

```shell
curl "https://api.gmodstore.com/v2/users/76561197988497435/badges" \
  -H "Authorization: Bearer secret"
```

```php
use GmodStore\API\Client;

$client = new Client('secret');

$client->getUser(76561197988497435)->getBadges();
```

> This endpoint requires the `users.read` permission

Fetch all the badges a user has.

`GET https://api.gmodstore.com/v2/users/<id>/badges`

**Route parameters:**

Name | Type | Description
---- | ---- | -----------
id | Integer | The SteamID of the user to fetch the badges of

Response code: `200`<br>
Response resource: [Collection](#resource-types-collection)<[UserBadgeLegend](#resource-types-user-badge-legend)>

### Store

```shell
curl -X POST "https://api.gmodstore.com/v2/users/76561197988497435/badges" \
  -H "Authorization: Bearer secret" \
  -d "badge=discord-booster"
```

```php
use GmodStore\API\Client;

$client = new Client('secret');

$client->getUser(76561197988497435)->giveBadge([
  'badge' => 'discord-booster',
]);
```

> This endpoint requires the `users.write` permission as well as the user permission to give a badge

Give a user a badge.

<aside class="warning">
This endpoint is only available to users who have the `give_badge` permission
</aside>

`POST https://api.gmodstore.com/v2/users/<id>/badges`

**Route parameters:**

Name | Type | Description
---- | ---- | -----------
id | Integer | The SteamID of the user to give the badge to

**Form fields:**

Name | Type | Description
---- | ---- | -----------
badge       | String       | The id of the User Badge Legend to give

Response code: `201`<br>
Response resource: [User Badge Legend](#resource-types-user-badge-legend)


### Destroy

```shell
curl -X DELETE "https://api.gmodstore.com/v2/users/76561197988497435/badges/discord-booster" \
  -H "Authorization: Bearer secret"
```

```php
use GmodStore\API\Client;

$client = new Client('secret');

$client->getUser(76561197988497435)->getBadge('discord-booster')->delete();
```

> This endpoint requires the `users.write` permission as well as the user permission to take a badge

Destroy a users's badge.

<aside class="warning">
This endpoint is only available to users who have the `take_badge` permission
</aside>

`DELETE https://api.gmodstore.com/v2/users/<user_id>/badges/badge_id>`

**Route parameters:**

Name | Type | Description
---- | ---- | -----------
id | Integer | The SteamID of the user the badge belongs to
badge_id       | String       | The id of the User Badge Legend to take

Response code: `204`
