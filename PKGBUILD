# This is an example PKGBUILD file. Use this as a start to creating your own,
# and remove these comments. For more information, see 'man PKGBUILD'.
# NOTE: Please fill out the license field for your package! If it is unknown,
# then please put 'unknown'.

# Maintainer: Grollicus <youremail@domain.com>
pkgname=mailgen
pkgver=0.2.0
pkgrel=1
pkgdesc="CLI tool that generates email addresses that are valid under a secret."
arch=('i686' 'x86_64')
url="https://github.com/Grollicus/recipientfilter"
license=('GPL3')
groups=()
depends=('rust')
makedepends=('cargo')
provides=()
conflicts=()
replaces=()
backup=()
options=()
install=
source=("https://github.com/Grollicus/recipientfilter/archive/v$pkgver.tar.gz")
noextract=()
sha256sums=('0fbab1ff16853ba2dbf5eef5354b8e9cec7e54c6feebd55263a14bb721b0bedb')

build() {
	cd "$srcdir/recipientfilter-${pkgver}/${pkgname}/"
	cargo build --release
}

clean() {
    cd "$srcdir/recipientfilter-${pkgver}/${pkgname}/"
	cargo clean
}

package() {
	cd "$srcdir/recipientfilter-${pkgver}/${pkgname}/"
    install -Dm755 "target/release/mailgen" "$pkgdir/usr/bin/mailgen"
}
