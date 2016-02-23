# No setuid on scripts

It's something I had already seen, the kernel doesn't allow setuid on
scripts, just like most modern unix systems.

It is designed to protect against some security issues related to the fact
that the name of the script is passed as argv[1] to the interpreter.

If you're able to switch the original name with a script you control,
you win.
[This incredible ressource](http://www.faqs.org/faqs/unix-faq/faq/part4/section-7.html)
lists at least two exploitation vectors that use this idea:

- ```
  $ ln setuid-script -i
  $ PATH=.
  $ -i
  ```

  A `#!/bin/sh` script would be called with `/bin/sh -i` giving you an
  interactive shell.

- ```
  $ ln setuid-script tmp
  $ nice -20 tmp &
  $ mv controlled-script tmp
  ```

  The principle here is that we are able to switch the link with our
  script that the interpreter will then call.

Perl [used to](http://perldoc.perl.org/perlsec.html) be an interpreter that
tried to work around this security consideration whith the help of a
`suidperl` binary, but it has since been
[deprecated](http://search.cpan.org/~shay/perl-5.20.2/pod/perl5120delta.pod#Deprecations).
