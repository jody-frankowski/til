# Tmux and environment variables

When you attach to a new or an existing tmux session, tmux will update its
environment variables according to its configuration `update-environment`.
By default this variable contains
"DISPLAY SSH_ASKPASS SSH_AUTH_SOCK SSH_AGENT_PID SSH_CONNECTION WINDOWID XAUTHORITY".

This can be a problem when you are trying to attach to a remote tmux session
which is a part of a X11 session because the original X11 environment variable
will be overwritten.
One easy fix is to a attach like so `tmux a -E`. The `-E` option will disable
the `update-environment` option.
