# PS4

`PS4` is an environment variable printed by Bash at the beginning of each line
during an execution trace. By default the value of `PS4` is `+` and it is
repeated by the number of levels of indirection.

With the following code:

```sh
#!/bin/bash
test-function () {
    echo "Inside function"
}

echo "Outside function"

test-function
```

Here is an example of a traced execution:

```sh
$ bash -x trace-test.sh
+ echo 'Outside function'
Outside function
+ test-function
+ echo 'Inside function'
Inside function

```

Now let's modify the `PS4` variable to show the script name, line number and function name:

```sh
$ export PS4='+(${BASH_SOURCE}:${LINENO}): ${FUNCNAME[0]:+${FUNCNAME[0]}(): }'
$ bash -x trace-test.sh
+(trace-test.sh:7): main(): echo 'Outside function'
Outside function
+(trace-test.sh:9): main(): test-function
+(trace-test.sh:4): test-function(): echo 'Inside function'
Inside function
```

Sources:

[Making xtrace more useful](http://wiki.bash-hackers.org/scripting/debuggingtips#making_xtrace_more_useful)  
[PS4](http://wiki.bash-hackers.org/syntax/shellvars#ps4)
