# Kernel Patches

The Gentoo community maintains multiple kernel patches. The project is called
`genpatches`. You can find the project homepage [here](https://dev.gentoo.org/~mpagano/genpatches/).

The patches are separated in three categories:

* base: Includes bug and security fixes.
* extras: Includes extra hardware support and features.
* experimental: Includes experimental patches.

Those patches are applied to all available kernels (ck-sources, gentoo-sources, hardened-sources,
tuxonice-sources), but the hardened-sources kernel only gets base patches.

The kernel ebuilds have options to define the patch set and the minor patch version:

```sh
K_WANT_GENPATCHES="base extras experimental"
K_GENPATCHES_VER="2"
```
