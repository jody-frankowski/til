# File attributes

I already knew about those, but I had never really remembered their names.
In unix systems file attributes can be used to set specific attributes
on files such as immutability or being append only.

On Linux they can be modified with `chattr` and shown with `lsattr`, but they
obviously need to be supported by the filesystems.
BSDs support the same idea but not the exact sames attributes. They can be
modified with `chflags` and displayed with `ls -lo`.

They are not to be confused with [extended attributes](https://en.wikipedia.org/wiki/Extended_file_attributes)
which are a whole other story.

Interestingly the efivars filesystem uses it to [prevent machine bricking with rm -rf /](https://git.kernel.org/cgit/linux/kernel/git/torvalds/linux.git/commit/?id=0389075ecfb6231818de9b0225d3a5a21a661171).
