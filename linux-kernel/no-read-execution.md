# No read rights execution

It is possible to execute a binary with no read rights. Contrary to scripts,
in the case of elf binaries the kernel takes charge of reading the binary.

Taking this in account, it may allow one to do interesting tricks such as
unreadable setuid binaries.

However something was tickling my mind when I saw that I was still able to
see the system calls with strace (setuid binary or not). Is it still possible
to read binary?
Turns out it is possible, even for root setuid ones, [this awesome reverseengineering stackexchange answer](http://reverseengineering.stackexchange.com/a/106)
explains how.
The main idea is to ptrace a fork before calling execve on the binary, and
finally to dump the binary from memory with PTRACE__PEEKTEXT.
