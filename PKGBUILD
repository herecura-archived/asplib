# $Id$
# Maintainer: BlackEagle <ike.devolder@gmail.com>>

pkgname=asplib
_commit=da66f51
pkgver=20160310.da66f51
pkgrel=1
pkgdesc="Achim's Signal Processing LIBrary"
arch=('i686' 'x86_64')
url='https://github.com/AchimTuran/asplib'
license=('GPL')
depends=('gcc-libs')
makedepends=('git' 'cmake')
source=("$pkgname::git://github.com/AchimTuran/asplib.git#commit=$_commit")
sha256sums=('SKIP')

pkgver() {
	cd "$pkgname"
	git log -1 --date=short --format="%cd.%h" | tr -d '-'
}

build() {
	cd "$pkgname"
	cmake \
		-DCMAKE_INSTALL_PREFIX=/usr \
		-DCMAKE_BUILD_TYPE=Release \
		-DBUILD_SHARED_LIBS=1
	make
}

package() {
	cd "$pkgname"
	make DESTDIR="$pkgdir/" install
}

