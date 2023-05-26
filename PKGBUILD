# Maintainer: David K david.dk949@gmail.com
pkgname=dmenu
pkgver="unknown"
pkgrel=0
pkgdesc="dmenu is an efficient dynamic menu for X."
arch=('x86_64')
url="https://github.com/dk949/$pkgname"
license=('MIT')
depends=()
makedepends=('ldc')
provides=('dmenu')
source=("git+$url")
md5sums=() #autofill using updpkgsums
sha256sums=('SKIP')

pkgver() {
    git -C "$pkgname" describe | sed 's/-/_/g'
}

build() {
    cd "$pkgname"
    make -j
}

package() {
    cd "$pkgname"

    make DESTDIR="$pkgdir/" PREFIX="/usr" install
    install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
