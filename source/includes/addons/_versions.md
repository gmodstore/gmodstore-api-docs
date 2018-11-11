## Versions

### Index

```shell
curl "https://api.gmodstore.com/v2/addons/565/versions" \
  -H "Authorization: Bearer secret"
```

```php
use GmodStore\API\Client;

$client = new Client('secret');

$client->getAddon(565)->getVersions();
```

> This endpoint requires the `addons.versions.read` permission

Fetch all the versions of an addon.

`GET https://api.gmodstore.com/v2/addons/<id>/versions`

**Route parameters:**

Name | Type | Description
---- | ---- | -----------
id | Integer | The id of the addon to fetch the versions of

Response code: `200`<br>
Response resource: [Collection](#resource-types-collection)<[Addon Version](#resource-types-addon-version)>


### Store

```shell
curl -X POST "https://api.gmodstore.com/v2/addons/565/versions" \
  -H "Authorization: Bearer secret" \
  -F "name=Prometheus 2" \
  -F "changelog=Made it a **lot** better ;)" \
  -F "file=@prometheus2.zip"
```

```php
use GmodStore\API\Client;

$client = new Client('secret');

$client->getAddon(565)->createVersion([
  'name' => 'Prometheus 2',
  'changelog' => 'Made it a **lot** better ;)',
  'file' => fopen('prometheus_2.zip', 'r')
]);
```

> This endpoint requires the `addons.versions.write` permission

Create a new version for an addon.

`POST https://api.gmodstore.com/v2/addons/<id>/versions`

**Route parameters:**

Name | Type | Description
---- | ---- | -----------
id | Integer | The id of the addon to create the coupon for

**Form fields:**

Name | Type | Description
---- | ---- | -----------
name      | String (1 - 80 chars)     | The name for the version
changelog | String (1 - 10,000 chars) | The changelog for the version
file      | File (zip)                | The file containing the addon

Response code: `201`<br>
Response resource: [Addon Version](#resource-types-addon-version)


### Show

```shell
curl "https://api.gmodstore.com/v2/addons/565/versions/6" \
  -H "Authorization: Bearer secret"
```

```php
use GmodStore\API\Client;

$client = new Client('secret');

$client->getAddon(565)->getVersion(6);
```

> This endpoint requires the `addons.versions.read` permission

Fetch a specific version of an addon.

`GET https://api.gmodstore.com/v2/addons/<addon_id>/versions/<version_id>`

**Route parameters:**

Name | Type | Description
---- | ---- | -----------
addon_id   | Integer | The id of the addon the version belongs to
version_id | Integer | The **id** of the version to fetch

Response code: `200`<br>
Response resource: [Addon Version](#resource-types-addon-version)


### Download

```shell
curl "https://api.gmodstore.com/v2/addons/565/versions/6/download" \
  -H "Authorization: Bearer secret"
```

```php
use GmodStore\API\Client;

$client = new Client('secret');

$client->getAddon(565)->getVersion(6)->getDownloadToken();
```

> This endpoint requires the `addons.versions.download` permission

Generate a download token for a specific version of an addon.

`GET https://api.gmodstore.com/v2/addons/<addon_id>/versions/<version_id>/download`

**Route parameters:**

Name | Type | Description
---- | ---- | -----------
addon_id   | Integer | The id of the addon the version belongs to
version_id | Integer | The **id** of the version to download

Response code: `200`<br>
Response resource: [Addon Download](#resource-types-addon-download)


### Update

```shell
curl -X POST "https://api.gmodstore.com/v2/addons/565/versions/6" \
  -H "Authorization: Bearer secret" \
  -d "name=Prometheus 1.8&changelog=April fools xD"
```

```php
use GmodStore\API\Client;

$client = new Client('secret');

$client->getAddon(565)->getVersion(6)->update([
  'name' => 'Prometheus 1.8',
  'changelog' => 'April fools xD',
]);
```

> This endpoint requires the `addons.versions.write` permission

Update a version of an addon.

`POST https://api.gmodstore.com/v2/addons/<addon_idid>/versions/<version_id>`

**Route parameters:**

Name | Type | Description
---- | ---- | -----------
addon_id   | Integer | The id of the addon the version belongs to
version_id | Integer | The **id** of the version to fetch

**Form fields:**

Name | Type | Description
---- | ---- | -----------
name      | String (1 - 80 chars)     | The new name for the version
changelog | String (1 - 10,000 chars) | The new changelog for the version

Response code: `200`<br>
Response resource: [Addon Version](#resource-types-addon-version)
