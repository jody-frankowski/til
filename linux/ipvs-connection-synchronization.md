# IPVS Connection Synchronization

As part of [LVS](http://www.linuxvirtualserver.org/), the
[IPVS Connection Synchronization](http://www.linuxvirtualserver.org/docs/sync.html)
daemon is used to synchronize the connections between the load balancer so
that a failover will not break the existing connections.

Just like vrrp, the states are advertised with udp multicast packets, but
with the 224.0.0.81 multicast address and with the 8848 destination port.

For performance reasons, this "daemon" is implemented as a kernel component,
rather than a userland process. You can see the kernel thread with ps
(notice the brackets):

```sh
$ ps aux | grep sync
root      6787  0.0  0.0      0     0 ?        S     2015  26:10 [ipvs_syncmaster]
```
