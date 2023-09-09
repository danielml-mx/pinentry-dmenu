# pinentry-dmenu

This is a simple shell script that integrates [dmenu-wayland](https://github.com/fabianscode/dmenu-wayland) with [GnuPG](https://gnupg.org/) as an alternative pinentry method.

## Installation

### Manual

To install this, do a `git clone https://github.com/fabianscode/pinentry-dmenu`, configure `config.mk` for your system and run `sudo make install`. Similarly, to uninstall run `sudo make uninstall`.

## Usage

To use dmenu as the pinentry program for GnuPG, configure `~/.gnupg/gpg-agent.conf` to use the full path of the `pinentry-dmenu` script:

```
pinentry-program /usr/local/bin/pinentry-dmenu (or whatever other path you chose)
```

The full path will depend on the `PREFIX` used in `config.mk`. 
