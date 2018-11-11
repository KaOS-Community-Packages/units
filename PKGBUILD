pkgname=units
pkgver=2.18
pkgrel=1
pkgdesc="Converts between different units"
arch=('x86_64')
url="http://www.gnu.org/software/units/units.html"
screenshot="http://konsole.kde.org/images/konsole_icon_48.png"
depends=('readline')
license=("GPL")
options=('!makeflags')
install=units.install
source=("http://ftp.gnu.org/gnu/units/$pkgname-$pkgver.tar.gz")
md5sums=('402395abfc0cc3bba6a76ee4c118bc72')

build() {
  cd $srcdir/$pkgname-$pkgver
  msg "### configure"
  ./configure --prefix=/usr --datadir=/usr/share
  msg "### make"
  make
}

package() {
  cd $srcdir/$pkgname-$pkgver
  msg "### make install"
  make DESTDIR=$pkgdir install
  _docdir=${pkgdir}/usr/share/doc/${pkgname}-${pkgver}
  _licdir=${pkgdir}/usr/share/licenses/${pkgname}
  install -dpm755 ${_docdir} ${_licdir}
  install -Dpm644 ChangeLog INSTALL NEWS README units.pdf units.txt ${_docdir}/
  install -Dpm644 COPYING ${_licdir}/
}
