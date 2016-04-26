# x-content-type-options

The `X-Content-Type-Options` HTTP header with the only value `nosniff` can be
used to tell the browser not to do
[MIME-type sniff](https://en.wikipedia.org/wiki/Content_sniffing).

According to [this owasp page](https://www.owasp.org/index.php/List_of_useful_HTTP_headers)
it can be used to avoid drive-by download attacks, but it is only leveraged
by Internet Explorer and Google Chrome.
