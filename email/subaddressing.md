# Subaddressing

I knew about
[subaddressing](https://en.wikipedia.org/wiki/Email_address#Sub-addressing), but
what I didn't know was that it's actually
an [entire RFC](https://tools.ietf.org/html/rfc5233)
([here is the original RFC from 2003](https://tools.ietf.org/html/rfc3598)).

In Postfix you can change the separator with the
*[recipient_delimiter](http://www.postfix.org/postconf.5.html#recipient_delimiter)*
parameter.

Likewise in [OpenSMTPD](https://www.opensmtpd.org/) you can change this
separator with the *[subaddressing-delimiter](http://man.openbsd.org/smtpd.conf)*.
