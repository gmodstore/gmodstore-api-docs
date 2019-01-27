# Authentication

> To authenticate, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "https://api.gmodstore.com/v2/<endpoint>" \
  -H "Authorization: Bearer secret"
```

```php
use GmodStore\API\Client;

$client = new Client('secret');
```

> Make sure to replace `secret` with your API key.

The Gmodstore provides two methods of authentication: bearer token and query parameter.

The preferred method is using the bearer token.
To do so simply set the `Authorization` header to `Bearer <api_key>` where `<api_key>` is your API key.

If you for some reason wish to use the API with the old way simply pass a query variable named `api_key` containing your API key.

<aside class="notice">
We recommend that you use the bearer token to authenticate.
</aside>

