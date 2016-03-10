# RS in awk

With awk, you can specify an arbitrary Record Separator.
You can use it to split records by blank lines, which is really handy
when the output of some command isn't parseable line-by-line.

It can be used when we need to delete mail in the postfix queue from or to
a specific email/domain:

```sh
postqueue -p | tail +2 | awk 'BEGIN { RS = "" } / @example\.com$/ { print $1 }' | tr -d '*!' | postsuper -d -
```
