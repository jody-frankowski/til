# `dmsetup`

You can use `dmsetup` and more specifically `dmsetup deps -o devname` to listing
the mappings between `/dev/mapper/` devices and `/dev/` original devices:

```
# dmsetup deps -o devname
cryptmain: 1 dependencies       : (sda3)
```
