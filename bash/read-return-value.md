# `read` return value

`read` won't return 0 when end-of-file is encountered:

> The  exit status is  zero, unless
> end-of-file is  encountered, read  times out  (in which
> case  the  status  is  greater than  128),  a  variable
> assignment  error  (such  as assigning  to  a  readonly
> variable)  occurs, or  an  invalid  file descriptor  is
> supplied as the argument to -u.

When `-d ''` is specified, the delimiter is set to a null string.
The following example will make `read` return 1:

```sh
read -d '' variable <<EOF
value
value
EOF
```

This can be a problem if you have `set -e` at the top of your script.
You can bypass this problem by temporarily doing `set +e`.
