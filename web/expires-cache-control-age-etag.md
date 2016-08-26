# Expires, Cache-Control, Age and Etag

In the http protocol, several headers were defined that helped control client
caching. One of them was `Expires` which gave a date when the client should
consider the cached asset to be expired. The problem with this header was
that it was an absolute date which wasn't reliable on many "buggy" systems.
That's why `Cache-Control` was introduced. It gives a time during which the
client can consider the asset to be up-to-date. If this header is specified,
modern browsers won't take `Expires` into account. If the `Age` is specified,
browsers will deduce this amount of time from the time in `Cache-Control`.
The `Etag` header associated with an asset can also be sent by a client to
let the server check and answer that the asset hasn't changed.

You can read more [here](http://www.mobify.com/blog/beginners-guide-to-http-cache-headers/)
and [here](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/http-caching?hl=en).
