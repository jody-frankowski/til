# Zpool Versions and Feature Flags

Zpool versions used to represent a set of features and an on-disk format.
When Oracle stopped development under an open-source license, the OpenZFS
project was created, and as a result of their distributed development model
they introduced `Feature Flags`. Those flags allow for a more portable on-disk
format.
The zpool version 5000 is a special version used by the OpenZFS project,
which is supposed to be the last version and describe a zpool version 28
with feature flags activated.

Find more info [here](https://en.wikipedia.org/wiki/ZFS#Detailed_release_history).
