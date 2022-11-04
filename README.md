## Running discord under nearly any electron version

### But electron version what is discord currently running
Currently electron is running electron version 13

### Using custom electron versions

#### Arch Linux
1. Install your prefered electron version (19, 20, 21 ,22)
2. Copy the [PKGBUILD](https://aur.archlinux.org/cgit/aur.git/plain/PKGBUILD?h=discord_arch_electron_wayland) from `discord_arch_electron_wayland` 
3. Edit this **PKGBUILD** and replace every `electron13` by you prefered version (ie. `electron22`)
4. Go to [openasar](https://openasar.dev) and download the **app.asar**
5. Copy this file to `/usr/lib/discord/app.asar` (overwrite the current file)
6. You can run discord
