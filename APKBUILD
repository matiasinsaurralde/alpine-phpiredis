# Contributor: Matias Insaurralde <matias@insaurral.de>
# Maintainer:
pkgname=phpiredis
pkgver=0
pkgrel=0
pkgdesc="PHP bindings for Hiredis (Redis client)"
url="https://github.com/nrk/phpiredis"
arch="all"
license="BSD"
depends="hiredis"
depends_dev="php-dev autoconf hiredis-dev"
makedepends="$depends_dev"
install=""
subpackages=""
source="https://github.com/nrk/phpiredis/archive/master.zip"

_builddir=${srcdir}/${pkgname}-master
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
	phpize
	./configure
}

package() {
	cd "$_builddir"
	make || return 1
	make INSTALL_ROOT=$pkgdir install || return 1
	install -d "$pkgdir"/etc/php/conf.d || return 1
	echo "extension=phpiredis.so" > "$pkgdir"/etc/php/conf.d/phpiredis.ini
}

md5sums="ea4cc29b3f55280150339a6b184c9c78  master.zip"
sha256sums="c7dec585c60a1b660596719fc3f50b7e9c836a0445ca9634b07590c4b9f8589a  master.zip"
sha512sums="4c22a56a63d4992027dda44bdd7042df867db664a32f43170240cf1aa114e81e0724a7fa6aeed76f127883e7b89be14602dae7cfb086ad77703bdee63c50dcc2  master.zip"
