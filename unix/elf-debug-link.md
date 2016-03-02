# ELF .gnu_debuglink section

This elf section is used by debuggers to find out the associated debug
file to the current elf.

It contains the name of the file, and a crc32 checksum of that file in
order to check it is the right debug build.

[This article](https://blogs.oracle.com/dbx/entry/gnu_debuglink_or_debugging_system)
contains more infos.
