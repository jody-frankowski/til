# ARC and L2ARC

`ARC` (Adaptive Replacement Cache) is a ZFS memory cache that can dramatically
improve reading performance. Thanks to
its
[own algorithm](http://open-zfs.org/wiki/Performance_tuning#Adaptive_Replacement_Cache),
it is able to provide a better hit ratio than a traditional LRU page cache.

The big brother of `ARC` is `L2ARC` which allows zfs to cache pages, the same
way as with `ARC`, but typically on SSD.

Further reading:

[https://www.zfsbuild.com/2010/04/15/explanation-of-arc-and-l2arc/](https://www.zfsbuild.com/2010/04/15/explanation-of-arc-and-l2arc/)
