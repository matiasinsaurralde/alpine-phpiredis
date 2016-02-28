# Contributor:
# Maintainer:
pkgname=phpiredis
pkgver=
pkgrel=0
pkgdesc=""
url=""
arch="all"
license=""
depends=""
depends_dev=""
makedepends="$depends_dev"
install=""
subpackages="$pkgname-dev $pkgname-doc"
source=""

_builddir=
prepare() {
	local i
	cd "$_builddir"
	for i in $source; do
		case $i in
		*.patch) msg $i; patch -p1 -i "$srcdir"/$i || return 1;;
		esac
	done
}

build() {
	cd "$_builddir"
}

package() {
	cd "$_builddir"
}

