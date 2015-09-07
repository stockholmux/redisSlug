# [redisSlug](https://github.com/stockholmux/redisSlug)

slugifies every string, even when it contains unicode with the power of Redis!

Make strings url-safe.

Forked from [slug](https://github.com/dodo/node-slug) to use Redis instead of storing the unicode table in-process. The unicode table is wildly large (~10mb of heap) and every process has to store and parse the table (which blocks for ~200ms on machine). By using Redis to store just the needed portions of the unicode table, multiple processes can share one unicode table with minimal speed impact.

As a consequence of using Redis, the calls are asynchronous and client-side code has been removed.

- respecting [RFC 3986](https://tools.ietf.org/html/rfc3986)
- Coerces foreign symbols to their english equivalent

Coming soon:
- Tests

```
npm install redis-slug
```