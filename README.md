# mitamae-build

[mitamae](https://github.com/itamae-kitchen/mitamae) binary distribution for various environments.

Version: 1.11.0

## Usage

```bash
arch=x86_64
os=freebsd
mitamae="mitamae-${arch}-${os}"

wget "https://github.com/itamae-kitchen/mitamae-solaris/releases/latest/download/${mitamae}"
chmod +x "$mitamae"
"./${mitamae}" help
```

## Release
### Servers

* 140.211.168.162 (power9)
* freebsd12.rubyci.org (x86\_64-freebsd)
* openbsd.rubyci.org (x86\_64-openbsd)
* solaris.rubyci.org
  * sol10 (sparc-solaris)

### Build
TODO

## Caveats

* The released binaries are manually built on rubyci servers.
  There's no well-maintained environment to automatically build mitamae binary for the environments.

* This repository's service level is low.
  Do not expect frequent releases for future mitamae versions.
