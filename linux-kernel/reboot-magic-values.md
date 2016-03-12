# reboot(2) syscall magic values

The reboot syscall takes two magic values as arguments, `magic` and `magic2`,
in order to avoid accidental calls to reboot, which can be quite a destructive
syscall.
The accepted value for `magic` is `0xfee1dead` and the accepted values for
`magic2` are:

- 0x28121969
- 0x05121996
- 0x16041998
- 0x20112000

The man page lists those values in decimal, but in hexadecimal, it becomes
quite clear that those are dates, and more specifically, in respective order,
the birth date of Linus, and his three daughters.
