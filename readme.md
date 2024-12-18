# pinentry-dmenu

This is a simple shell script that integrates [dmenu](https://tools.suckless.org/dmenu/) with [GnuPG](https://gnupg.org/) as an alternative pinentry method. This program requires that dmenu be patched with the [password patch](https://tools.suckless.org/dmenu/patches/password/). There is additional optional functionality that depends on the [center](https://tools.suckless.org/dmenu/patches/center/) patch.

This was forked from [fabianscode/pinentry-dmenu](https://github.com/fabianscode/pinentry-dmenu) since some changes made to it made it incompatible with a default installation of dmenu (non-Wayland) with the password patch. 

It is worth noting that this script is unrelated to the one found in the Arch User Repository of the same name, since that one builds its own binary of dmenu with the password patch. This one expects a binary to already be installed. By the way, if someone wishes to make an AUR package of this project, please go ahead.

## Installation

### Manual

To install this, do a `git clone https://github.com/danielml-mx/pinentry-dmenu.git`, configure `config.mk` for your system and run `sudo make install`. Similarly, to uninstall run `sudo make uninstall`.

To have the prompt centered on your screen, uncomment the option in the actual script before installing. Again, this depends on the center patch for dmenu.

## Usage

To use dmenu as the pinentry program for GnuPG, configure `$GNUPGHOME/gpg-agent.conf` to use the full path of the `pinentry-dmenu` script:

```
pinentry-program /usr/local/bin/pinentry-dmenu (or whatever other path you chose)
```

The full path of the script will depend on the `PREFIX` used in `config.mk`. 
