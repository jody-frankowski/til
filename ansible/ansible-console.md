# ansible-console

Since the version 2.1 of ansible there exists a new tool called `ansible-console`.
As the [changelog](https://github.com/ansible/ansible/blob/devel/CHANGELOG.md)
states, this is a REPL shell that can be used to run modules or commands against a
set of hosts/groups.

```shell
$ ansible-console group-name
Welcome to the ansible console.
Type help or ? to list commands.

me@group-name (2)[f:5]$ ping
host-a | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
host-b | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
```

You can also call commands directly:

```shell
me@group-name (2)[f:5]$ uptime
host-a | SUCCESS | rc=0 >>
 16:39:03 up 64 days, 22:21,  1 user,  load average: 0.17, 0.18, 0.21

host-b | SUCCESS | rc=0 >>
 16:39:03 up 76 days, 18:47,  1 user,  load average: 0.29, 0.26, 0.27
```
