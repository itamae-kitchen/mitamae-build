# mitamae-build

[mitamae](https://github.com/itamae-kitchen/mitamae) binary distribution for various environments.

Version: 1.12.4

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

* 140.211.168.162 (ppc64le-linux)
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
# Upload `mruby/build/host/bin/mitamae` to GitHub
```

## Caveats

* The released binaries are manually built on rubyci servers.
  There's no well-maintained environment to automatically build mitamae binary for the environments.

* This repository's service level is low.
  Do not expect frequent releases for future mitamae versions.
