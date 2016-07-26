# File Creation Time

Some Linux file systems store the creation time of files. It won't show
with `stat` because the GNU stat and ls tools are waiting for the `xstat(2)`
system call.

You can see the timestamp of a file on a ext4 partition with the debugfs command:

```
debugfs -R 'stat <398264>' /dev/sda2
debugfs 1.42.5 (29-Jul-2012)
Inode: 398264   Type: regular    Mode:  0644   Flags: 0x80000
Generation: 2058737571    Version: 0x00000000:00000001
User:     0   Group:     0   Size: 562
File ACL: 0    Directory ACL: 0
Links: 1   Blockcount: 8
Fragment:  Address: 0    Number: 0    Size: 0
ctime: 0x506b860b:19fa3c34 -- Wed Oct  3 02:25:47 2012
atime: 0x50476677:dcd84978 -- Wed Sep  5 16:49:27 2012
mtime: 0x506b860b:19fa3c34 -- Wed Oct  3 02:25:47 2012
crtime: 0x50476677:dcd84978 -- Wed Sep  5 16:49:27 2012
Size of extra inode fields: 28
EXTENTS:
(0):3308774
```

More info [in this lwn article](https://lwn.net/Articles/397442/) and
[this unix.stackexchange.com answer](https://unix.stackexchange.com/questions/50177/birth-is-empty-on-ext4/50184#50184)>
