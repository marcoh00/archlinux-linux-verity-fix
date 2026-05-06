# Arch Linux `linux` package with overlayfs+verity fix

Currently, bootc is unusable with vanilla 7.0 kernels, as commit [f77f281b61183a5c0b87e6a4d101c70bd32c1c79](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=f77f281b61183a5c0b87e6a4d101c70bd32c1c79) introduces a regression that makes it impossible to access verity protected files on overlayfs when verity=require is set.

This kernel build applies the proposed patch by Colin Walters and Eric Biggers from https://lore.kernel.org/fsverity/20260505224257.23213-1-ebiggers@kernel.org/T/#u

Using this patched kernel is a workaround for [bootc-dev/bootc#2174](https://github.com/bootc-dev/bootc/issues/2174).

# Repository

You can use this repository in order to build a package as part of your container build or use precompiled packages:

```
[archlinux-linux-verity-fix]
SigLevel = Optional
Server = https://github.com/marcoh00/archlinux-linux-verity-fix/releases/download/current
```

And install them:

```
pacman -Sy
pacman -S archlinux-linux-verity-fix/linux
```
