# Rate Limiting

The Handwrite API is rate limited to prevent abuse that would degrade our ability to maintain consistent API performance for all users.

By default, each API key is rate limited at 60 requests per minute. If your requests are being rate limited, HTTP response code `429` will be returned with an `rate_limit_exceeded` error.

In your response headers, you should see information pertaining to your limits at any given time.

| Header                             | Description                                                                       |
| ---------------------------------- | --------------------------------------------------------------------------------- |
| <code>X-RateLimit-Limit</code>     | The maximum number of requests that the consumer is permitted to make per minute. |
| <code>X-RateLimit-Remaining</code> | The number of requests remaining in the current rate limit window.                |
| <code>X-RateLimit-Reset</code>     | The time at which the current rate limit window resets.                           |
