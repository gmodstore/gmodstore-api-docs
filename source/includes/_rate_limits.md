# Rate Limits

Every request you make to the Gmodstore API will count against your rate limit which, as of the time of writing, is 60 requests / minute.<br>
An up-to-date value will always provided in the `X-RateLimit-Limit` header.<br>
The number of requests you have remaining before you must wait is provided in the `x-RateLimit-Remaining` header.
