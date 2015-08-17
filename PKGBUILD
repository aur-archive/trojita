# Maintainer: birdflesh <antkoul at gmail dot com>

pkgname=trojita
pkgver=0.4.1
pkgrel=1
pkgdesc="A QT IMAP email client"
arch=('i686' 'x86_64')
url="http://trojita.flaska.net"
license=('GPL')
makedepends=('cmake' 'automoc4')
depends=('qtwebkit')
install=$pkgname.install
source=(http://downloads.sourceforge.net/$pkgname/$pkgname-$pkgver.tar.bz2)
md5sums=('130c9e51bb71564511ab123f88236850')

build() {
  cd "$srcdir"
  mkdir build
  cd build
  cmake ../$pkgname-$pkgver \
    -DQT_QMAKE_EXECUTABLE=qmake-qt4 \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/usr
  make
}

package() {
  cd "$srcdir/build"
  make DESTDIR="$pkgdir" install
}
