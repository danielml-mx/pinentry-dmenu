# pinentry-dmenu

This is a simple shell script that integrates [dmenu](https://tools.suckless.org/dmenu/) with [GnuPG](https://gnupg.org/) as an alternative pinentry method. This program assumes a pre-existing dmenu installation patched with the [password patch](https://tools.suckless.org/dmenu/patches/password/) and the [center](https://tools.suckless.org/dmenu/patches/center/) patch.

This was forked from [fabianscode/pinentry-dmenu](https://github.com/fabianscode/pinentry-dmenu) since some changes made to it made it incompatible with a default installation of dmenu with the password patch. 

## Installation

### Manual

To install this, do a `git clone https://github.com/danielml-mx/pinentry-dmenu.git`, configure `config.mk` for your system and run `sudo make install`. Similarly, to uninstall run `sudo make uninstall`.

### AUR

This package has been added to the AUR as [`pinentry-dmenu-centered-git`](https://aur.archlinux.org/packages/pinentry-dmenu-centered-git). You may install it with the AUR helper of your choice.

## Usage

To use dmenu as the pinentry program for GnuPG, configure `$GNUPGHOME/gpg-agent.conf` to use the full path of the `pinentry-dmenu` script. The full path of the script will depend on the `PREFIX` used in `config.mk`.

- For a local installation (default):
```
pinentry-program /usr/local/bin/pinentry-dmenu
```

- For an AUR installation:
```
pinentry-program /usr/bin/pinentry-dmenu
```

## Final note

I very rarely interface with this program nowadays. I use [`pam-gnupg`](https://github.com/cruegge/pam-gnupg) to pass my login password to the `gpg-agent` and have followed the recommendations provided in the repo so that the passphrase cache expires after a day.

