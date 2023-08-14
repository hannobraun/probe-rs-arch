# probe-rs Arch Linux package

This is an experimental Arch package for probe-rs. **Please note that the existence of this repository does not apply that there is a probe-rs package in the official Arch repositories or the AUR.** This is just a first step towards figuring out how to package probe-rs for Arch.

This package was created based on the following documentation:

- [https://wiki.archlinux.org/title/PKGBUILD](https://wiki.archlinux.org/title/PKGBUILD)
- [https://wiki.archlinux.org/title/Rust_package_guidelines](https://wiki.archlinux.org/title/PKGBUILD)


## Installation

To install this package, run the following command from the repository root:

```
makepkg -si
```


## Updating

To keep the package updated, the following parts of `PKGBUILD` need to be changed:

- `pkgver`: This should always be the [latest version of probe-rs on crates.io](https://crates.io/crates/probe-rs).
- `sha256sums`: These must match the files specified in `source`. You can generate the `sha256sums` for the currently referenced sources with `makepkg -g`.
- Other parts of `PKGBUILD` or `probe-rs.install` might need to be updated, if anything changes in a significant way. But for routine upgrades, that should be it.


## Open Questions

`PKGBUILD` doesn't specify any native dependencies (see `depends`), but I'm pretty sure some are needed.
