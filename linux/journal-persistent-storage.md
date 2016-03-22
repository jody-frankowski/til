# Journal Persistent Storage

On [CentOS 7](https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/7/html/System_Administrators_Guide/s1-Using_the_Journal.html#s2-Enabling_Persistent_Storage)
and [Debian 8](https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=717388), you have to
manually enable journal persistent storage) otherwise you won't be able to see
older boots logs for example.

According to [this stackexchange answer](http://unix.stackexchange.com/a/232878)
you also have to call `systemd-tmpfiles --create --prefix /var/log/journal`
after `mkdir /var/log/journal` in order to set the proper rights and ownership.
