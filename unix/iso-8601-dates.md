# ISO 8601

One easy way to generate [ISO 8601 dates](https://en.wikipedia.org/wiki/ISO_8601)
is to use the `date` command with the argument `-I` or `--iso-8601`:

```
date -I
2016-07-22
```

You can add the time by specifying the precision (up to nanoseconds) like so:

```
date --iso-8601=minutes                                                                                                                                                                                                          [12:57:53]
2016-07-22T12:57+02:00
```
