# debuginfo-install

On CentOS/RHEL there is this neat little tool, `debuginfo-install`.
It can be found in the `yum-utils` package, and you can use it to download
the '-debuginfo' package of any version of any package and its dependencies.

What is really nice about this tool, it's that CentOS' gdb has been modified
to warn about missing symbols and propose the right `debuginfo-install` command:

```sh
# gdb -p pid-httpd
<...>
Reading symbols from /usr/lib64/perl5/vendor_perl/auto/Data/UUID/UUID.so...(no debugging symbols found)...done.
Loaded symbols for /usr/lib64/perl5/vendor_perl/auto/Data/UUID/UUID.so
0x00007f686ad7bf13 in __epoll_wait_nocancel () from /lib64/libc.so.6
Missing separate debuginfos, use: debuginfo-install httpd-2.2.15-47.el6.centos.1.x86_64

# debuginfo-install httpd-2.2.15-47.el6.centos.1.x86_64
<...>
Installing:
 apr-debuginfo                                                    x86_64                                1.3.9-5.el6_2                                           base-debuginfo                                374 k
 apr-util-debuginfo                                               x86_64                                1.3.9-3.el6_0.1                                         base-debuginfo                                343 k
 db4-debuginfo                                                    x86_64                                4.7.25-20.el6_7                                         base-debuginfo                                6.8 M
 expat-debuginfo                                                  x86_64                                2.0.1-11.el6_2                                          base-debuginfo                                171 k
 glibc-debuginfo                                                  x86_64                                2.12-1.166.el6_7.3                                      base-debuginfo                                8.7 M
 httpd-debuginfo                                                  x86_64                                2.2.15-47.el6.centos.1                                  base-debuginfo                                2.7 M
 libselinux-debuginfo                                             x86_64                                2.0.94-5.8.el6                                          base-debuginfo                                560 k
 openldap-debuginfo                                               x86_64                                2.4.40-7.el6_7                                          base-debuginfo                                4.3 M
 pcre-debuginfo                                                   x86_64                                7.8-7.el6                                               base-debuginfo                                372 k
 yum-plugin-auto-update-debug-info                                noarch                                1.1.30-30.el6                                           base                                           25 k
 zlib-debuginfo                                                   x86_64                                1.2.3-29.el6                                            base-debuginfo                                196 k
Installing for dependencies:
 glibc-debuginfo-common                                           x86_64                                2.12-1.166.el6_7.3                                      base-debuginfo                                8.3 M
```

As you can see it installed all the assiocated '-debuginfo' packages of
the dependencies of httpd in this case.
Once you have run this command and installed all the needed packages, gdb
should find all the debug symbols it needs.
