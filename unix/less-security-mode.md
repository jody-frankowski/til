# Less Security Mode

`less` offers a convenient security mode that can used for example in `sudo`
authorized commands:

```
SECURITY
       When the environment variable LESSSECURE is set to 1, less runs in a "secure" mode.  This means these features are disabled:

              !      the shell command

              |      the pipe command

              :e     the examine command.

              v      the editing command

              s  -o  log files

              -k     use of lesskey files

              -t     use of tags files

                     metacharacters in filenames, such as *

                     filename completion (TAB, ^L)
```
