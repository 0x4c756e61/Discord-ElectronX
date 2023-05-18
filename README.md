## Running discord under nearly any electron version

### But what electron version is discord currently running under ?
Currently discord stable is running electron version 22.3.2

### Using custom electron versions

#### Arch Linux
1. Install your prefered electron version (19, 20, 21 ,22)
2. Copy the [PKGBUILD](https://aur.archlinux.org/cgit/aur.git/plain/PKGBUILD?h=discord_arch_electron_wayland) from `discord_arch_electron_wayland` 
3. Edit this **PKGBUILD** and replace every `electron13` by you prefered version (ie. `electron22`), using sed: `sed -i 's/electron13/electron22/g' PKGBUILD`
4. Go to [openasar](https://openasar.dev) and download the **app.asar**
5. Copy this file to `/usr/lib/discord/app.asar` (overwrite the current file)
6. You can run discord

#### Any other linux distro
1. Install your prefered electron version (19, 20, 21 ,22)
2. Download the latest [discord version](https://discord.com) (use the tar.gz)
3. Unpack it
4. Go to [openasar](https://openasar.dev) and download the **app.asar**
5. Replace the `Discord/resources/app.asar` with the one download on step 4
6. While you can now run discord using your prefered electron version I recomend moving this whole folder to a system dir (requires su permissions) like `/usr/bin`
7. Create a basic script like this in a folder wich is in your PATH (like `/bin` or `/usr/bin`)
```sh
cd /usr/bin/discord/resources/
electron22 app.asar
```
8. give it executable permissions `chmod +x /usr/bin/discord.sh`
9. Create a desktop entry file in your `/usr/share/applications` directory (needs su permission)
```sh
[Desktop Entry]
Name=Discord
StartupWMClass=discord
Comment=All-in-one voice and text chat for gamers that's free, secure, and works on both your desktop and phone.
GenericName=Internet Messenger
Exec=/usr/bin/discord
Icon=discord
Type=Application
Categories=Network;InstantMessaging;
Path=/usr/bin
```
10. Should now be available in your app menu (may need to login again)

#### Windows
1. Download electron from it's [release page over on github](https://github.com/electron/electron/releases), the zip file to download should be name like so `electron-vVERSION-NUMER-win32-x64.zip`
2. Unzip the file to your desired directory
3. Download and execute the openasar installer from it's [website](https://openasar.dev)
4. Open a terminal (CMD or powershell) back in the electron directory unziped in step 2 and run `.\electron.exe C:\Users\YOUR-USERNAME-HERE\AppData\Local\Discord\app-1.0.9007\resources\app.asar`, alternatively you can just replace this long path with `%localappdata%\Discord\app-1.0.9007\resources\app.asar` if you are using CMD
5. I recommend creating a script and then creating a shortcut on your desktop with a custom icon
6. You can now run discord using the downloaded electron version
