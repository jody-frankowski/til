# iptables-apply

This is a wrapper command that will apply the iptables rules more safely,
namely it will prompt you to check that your established connection isn't
blocked, and at the same time ask to perform a 'NEW' connection.
If you fail to answer, iptables-apply will revert to the old rules.
However this script is only shipped with the Debian package `iptables`.
