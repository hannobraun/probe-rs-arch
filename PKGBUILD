pkgname=probe-rs
pkgver=0.20.0
pkgrel=1

pkgdesc="a modern, embedded debugging toolkit, written in Rust"
arch=('x86_64')
url="https://probe.rs/"
license=('MIT' 'Apache')

# TODO: No idea which non-Rust dependencies are required.
depends=()
makedepends=(cargo)

source=("$pkgname-$pkgver.tar.gz::https://static.crates.io/crates/$pkgname/$pkgname-$pkgver.crate")
sha256sums=('da6dec485ee49527950926fc3634980c7acb88b22dfb3b45b727ecc4d32e4298')

prepare() {
    export RUSTUP_TOOLCHAIN=stable

    cd "$pkgname-$pkgver"
    cargo fetch --locked --target "$CARCH-unknown-linux-gnu"
}

build() {
    export RUSTUP_TOOLCHAIN=stable
    export CARGO_TARGET_DIR=target

    cd "$pkgname-$pkgver"
    cargo build --locked --offline --release --features=cli
}

package() {
    cd "$pkgname-$pkgver"
    install -Dm0755 -t "$pkgdir/usr/bin/" "target/release/$pkgname"
}
