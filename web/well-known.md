# .well-known ([RFC 5785](https://tools.ietf.org/html/rfc5785))

The RFC 5785 describes a top directory that should be used for storing
files containing "site-wide metadata".

Let's Encrypt uses "/.well-known/acme-challenge/" to place the challenges it needs to
authenticate the server.

A DNT policy file can also be placed in "/.well-known/dnt/"

[Here is a list](https://www.iana.org/assignments/well-known-uris/well-known-uris.xhtml) of Well-Known URIs maintained by the IANA.
