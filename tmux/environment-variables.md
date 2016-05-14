# Tmux and environment variables

When you attach to a new or an existing tmux session, tmux will update its
environment variables according to its configuration `update-environment`.
By default this variable contains
"DISPLAY SSH_ASKPASS SSH_AUTH_SOCK SSH_AGENT_PID SSH_CONNECTION WINDOWID XAUTHORITY".
