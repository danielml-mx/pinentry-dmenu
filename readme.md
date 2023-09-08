# pinentry-dmenu

This is a simple shell script that integrates [suckless](https://suckless.org/)' [dmenu](https://tools.suckless.org/dmenu/) with [GnuPG](https://gnupg.org/) as an alternative pinentry method.

## Installation

### Manual

To install this, do a `git clone https://github.com/fabianscode/pinentry-dmenu`, configure `config.mk` for your system and run `sudo make install`. Similarly, to uninstall run `sudo make uninstall`.

## Usage

Firstly, you will need a dmenu build with the [password](https://tools.suckless.org/dmenu/patches/password/) patch applied, otherwise dmenu will not show up when used as the pinentry program.

Then, to use dmenu as the pinentry program for GnuPG, configure `~/.gnupg/gpg-agent.conf` to use the full path of the `pinentry-dmenu` script:

```
pinentry-program /usr/bin/pinentry-dmenu
```

The full path will depend on the `PREFIX` used in `config.mk`. The above example would apply to users who installed the AUR package, but by installing it with `make` with the default `PREFIX` installs it to `/usr/local/bin/pinentry-dmenu`.
