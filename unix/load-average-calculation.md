# How load average is calculated in different unix systems

This [awesome blogpost](https://utcc.utoronto.ca/~cks/space/blog/unix/ManyLoadAveragesOfUnix)
details how the different unix systems calculate the system load average.

In a nutshell:

    - On Linux the load average is the count of running process plus
    processes in short term io wait.
    - On FreeBSD the load average is the count of running processes.
    - On NetBSD the load average is the count of running processes and
    all processes that have slept for less than one second.
    - On OpenBSD the load average is the count of running processes and
    all processes in high priority IO wait that have slept for less than
    one second.

I'm only paraphrasing Chris' awesome work. For me it just points out once
more that we shouldn't trust our instinct, and check everything.
