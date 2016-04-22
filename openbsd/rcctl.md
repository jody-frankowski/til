# rcctl

On OpenBSD (since 5.7) you can use `rcctl` to manage daemons/services.
Editing `/etc/rc.conf.local` will still work.

Examples:

```sh
rcctl enable nginx
rcctl start nginx
rcctl check nginx
rcctl stop nginx
```
