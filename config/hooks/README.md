# ISO customization hooks

Put executable `.hook.chroot` files in this directory to run commands inside the live filesystem during the ISO build.

Example later:

```bash
#!/bin/sh
set -e
apt-get update
apt-get install -y curl git
```

You can also place files directly under `config/includes.chroot/` to have them copied into the ISO filesystem.
