# `ceph osd set noout`

This command allows you to make maintenance operations on your osd without
having CRUSH automatically rebalancing the cluster.
PGs will stay in a degraded state until you restart your OSDs and unset 'noout':

```sh
ceph osd unset noout
```
