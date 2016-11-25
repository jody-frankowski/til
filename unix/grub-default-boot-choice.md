# Grub Default Boot Choice

Grub can be quite tricky to configure to change the default boot choice.
One nice option is `GRUB_DEFAULT` in /etc/default/grub. You can set this
to a number starting from zero which corresponds to menu entries. Or
to `saved` and then the default menu entry will correspond to the value
saved by 'GRUB_SAVEDEFAULT', `grub-set-default` or `grub-reboot`.

If you set `GRUB_DEFAULT` to `saved` and `GRUB_SAVEDEFAULT` to `true` then
the next time you boot, the menu entry you choose will be saved and will
be the next default.
