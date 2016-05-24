# Setting the Mirror URL

In OpenBSD there is two way to set to URL used to fetch packages. The first
one and the most known is the environment variable `PKG_PATH` that can be
set like the following:

```
export PKG_PATH=http://a.local.mirror/$(uname -r)/packages/$(uname -m)/
echo "export $PKG_PATH" >> ~/.profile
```

People usually set it in their `.profile` file so that it's automatically
set in their shell.
Another, lesser known way to achieve this is to just set the variable
`installpath` in `/etc/pkg.conf`:

```
echo "installpath = http://a.local.mirror/$(uname -r)/packages/$(uname -m)/" > /etc/pkg.conf
```

On newer versions of OpenBSD you can even do it this way:

```
echo 'installpath = a.local.mirror' > /etc/pkg.conf
```

It will use the standard "/pub/OpenBSD/VERSION/packages/ARCH" directory layout
as documented [here](http://www.openbsd.org/faq/faq15.html#Easy)
