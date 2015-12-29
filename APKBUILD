# Contributor: Grant McLendon <grant@rightsup.com>
# Maintainer: Grant McLendon <grant@rightsup.com>
pkgname=libcouchbase
pkgver=2.5.4
pkgrel=0
pkgdesc="libcouchbase"
url="https://github.com/couchbase/libcouchbase"
arch="all"
license="ASL 2.0"
dependes="libstdc++"
depends_dev="libev-dev"
makedepends="$depends_dev cmake perl"
install=""
subpackages="$pkgname-doc $pkgname-dev"
source="$pkgname-$pkgver.tar.gz::https://github.com/couchbase/libcouchbase/archive/$pkgver.tar.gz"

_builddir="$srcdir"/$pkgname-$pkgver

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
  ./configure.pl \
    --prefix=/usr || return 1
  make || return 1
}

package() {
  cd "$_builddir"
  make DESTDIR="${pkgdir}" install || return 1
}
md5sums="1f39eae49509c84300e1c325f0efa652  libcouchbase-2.5.4.tar.gz"
sha256sums="06c0b25d7cb8ae9cfc52adefaa293d4b8f0dbef870bb64af261b714c1b1cb9fd  libcouchbase-2.5.4.tar.gz"
sha512sums="9b20699ced43e066df95c68228fb34e622f6383a26f7804ee4d88563a49d3d855c240314c61a100a0152ef64eea1a1ec513edc914adbb68ea7dc3f39114f8a62  libcouchbase-2.5.4.tar.gz"
