# org.gtimelog.GTimeLog
This repo contains the manifest file required to build [GTimeLog](https://gtimelog.org/) as a [Flatpak](https://flatpak.org/).
## Build
1. Make sure flatpak is installed in your system.
2. Clone this repository.
3. Run `flatpak-builder --user --install gflatlog org.gtimelog.GTimeLog/org.gtimelog.GTimeLog.json`.

This command will build the flatpak according to the manifest file `org.gtimelog.GTimeLog/org.gtimelog.GTimeLog.json` using `gflatlog` as the build directory. Then it will install it as the user.

For information on alternative ways to build (e.g. to a local repo), refer to the Flatpak [documentation](http://docs.flatpak.org/en/latest/).
## Issues
For both of these issues, someone who has Distutils experience may be helpful.
### App icon does not work
I tried installing the app icon the way the desktop file is installed but I could not make Flatpak see it. 
### Setup file references /app directly
In setup.py, /app is referenced directly for data_files. I thought setup would install relative to the installation prefix when it is left out but I could not get Flatpak to see the desktop file with a relative path. 

This issue prevents the patch from being upstreamed and since manifest does not work without the patch, the manifest also cannot be upstreamed.
