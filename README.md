# mitamae-build

[mitamae](https://github.com/itamae-kitchen/mitamae) binary distribution for various environments.

Version: 1.14.4

## Usage

```bash
arch=$(uname -m)
os=$(uname -s | tr '[:upper:]' '[:lower:]') # except SunOS => Solaris
mitamae="mitamae-${arch}-${os}"

wget "https://github.com/itamae-kitchen/mitamae-solaris/releases/latest/download/${mitamae}"
chmod +x "$mitamae"
"./${mitamae}" help
```

## Release
### Servers

* ppc64le.rubyci.org (ppc64le-linux)
* s390x.rubyci.org (s390x-linux)
* freebsd12.rubyci.org (x86\_64-freebsd)
* openbsd.rubyci.org (x86\_64-openbsd)
* solaris.rubyci.org
  * sol10 (sparc-solaris)

### Build

```bash
git clone https://github.com/itamae-kitchen/mitamae /tmp/mitamae
cd /tmp/mitamae
git checkout vX.Y.Z
rake compile
```

or for OpenBSD

```bash
ln -s /usr/local/bin/egcc /usr/local/bin/gcc # for muruby-yaml
AUTOCONF_VERSION=2.69 AUTOMAKE_VERSION=1.12 rake compile
```

Upload `mruby/build/host/bin/mitamae` to GitHub as `mitamae-${arch}-${os}` after building binaries on each server.

## Caveats

* The released binaries are manually built on rubyci servers.
  There's no well-maintained environment to automatically build mitamae binary for the environments.

* This repository's service level is low.
  Do not expect frequent releases for future mitamae versions.
