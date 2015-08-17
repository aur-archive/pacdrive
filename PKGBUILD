# Maintainer: NiteHogg <keith.b.elliott [at] gmail [dot] com>

# Custom properties used in PKGBUILD and auto-package creation.
_filename_exp=pacdrive_#_#
_category='system'

pkgname=pacdrive
pkgver=0.2
pkgrel=2
pkgdesc="Utility for interfacing with a pac-drive."
arch=('any')
url="http://www.zumbrovalley.net/pacdrive/"
license=('GPL')
depends=('libhid')
changelog=ChangeLog
source=("http://www.zumbrovalley.net/pacdrive/dnld/pacdrive_0_2.tar.gz")
md5sums=('5c6474a12955c6f52f6792f7380d19d1')

build() {

  cd "$srcdir/pacdrive_0_2"
  
  sed -r 's|(install:.*)man_5install man_8install|\1|g;s|(BINDIR=).*(/usr/bin)|\1$(DESTDIR)\2|g' Makefile > Makefile.NEW
  mv Makefile.NEW Makefile

  make
}

package() {
 
  mkdir -pv $pkgdir/usr/bin

  cd "$srcdir/pacdrive_0_2"
  make DESTDIR="$pkgdir/" install
}

# vim:set ts=2 sw=2 et:
