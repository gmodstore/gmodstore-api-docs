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
Whilst the former is preferred, you may still wish to use the latter, 
to do so simply pass a query variable named `api_key` containing your API key.
If you wish to use the former simply set the `Authorization` header to `Bearer <api_key>` where `<api_key>` is your API key.
