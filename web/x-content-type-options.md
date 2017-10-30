# X-Content-Type-Options

The `X-Content-Type-Options` HTTP header with the only value `nosniff` can be
used to tell the browser not to do
[MIME-type sniff](https://en.wikipedia.org/wiki/Content_sniffing).

According to [this Firefox blogpost](https://blog.mozilla.org/security/2016/08/26/mitigating-mime-confusion-attacks-in-firefox/)
it can be used to limit some XSS attacks.

Further read:

* [OWASP page](https://www.owasp.org/index.php/OWASP_Secure_Headers_Project#xcto)
