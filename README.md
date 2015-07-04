splash
======

To enable the boot splash image

1. add `splash` to your kernel command line
2. add the `systemd` and `sd-splash` hooks to your `mkinitcpio.conf`
3. place a framebuffer dump at `/etc/splash.fb` (e.g. using the `mksplash` tool)
