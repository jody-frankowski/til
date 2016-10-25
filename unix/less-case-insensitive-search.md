# Less Case Insensitive Search

To enable case insensitive search in `less`, you just have to start it with
the `-i` flag. In order to enable it while `less` is running you can use this
trick documented in the man page:

```
-     Followed  by one of the command line option letters (see OPTIONS below), this will change the setting of that option and print a message
      describing the new setting.  If a ^P (CONTROL-P) is entered immediately after the dash, the setting of the option is changed but no mes‐
      sage  is printed.  If the option letter has a numeric value (such as -b or -h), or a string value (such as -P or -t), a new value may be
      entered after the option letter.  If no new value is entered, a message describing  the  current  setting  is  printed  and  nothing  is
      changed.
```

So you can enable case insensitive search while running `less` by just typing
`-i`. `-i` enables "smart" case insensitive search, meaning that if there is an
uppercase letter in the search, the search will be case sensitive. You can
prevent this behavior by using the `-I` flag.
One other cool thing in `less` is that if you have already made your search,
when you will enable the `-i` flag, `less` will immediately highlight the new
matching patterns.
