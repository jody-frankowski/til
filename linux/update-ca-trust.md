# `update-ca-trust`

You can easily add another CA certificate to your local CAs with
`update-ca-trust` (others/older distributions may use `update-ca-certificates`).

You just have to first add the custom certificate in
`/etc/ca-certificate/trust-source/anchors/` (possibly
`/usr/local/share/ca-certificates/` in others/older distributions):

```sh
sudo mv custom.crt /etc/ca-certificate/trust-source/anchors/
```

Then issue the said command:

```sh
sudo update-ca-trust
```

And you're done!
