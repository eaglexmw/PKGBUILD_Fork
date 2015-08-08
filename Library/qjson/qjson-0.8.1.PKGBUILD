# $Id$
# Maintainer: Andrea Scarpino <andrea@archlinux.org>

pkgname=qjson
pkgver=0.8.1
pkgrel=3
pkgdesc="A qt-based library that maps JSON data to QVariant objects"
arch=('i686' 'x86_64')
license=('GPL')
url="http://qjson.sourceforge.net"
#depends=('qt4')
makedepends=('cmake')
options=('staticlibs')
source=(${pkgname}-${pkgver}.tar.gz::"https://github.com/flavio/${pkgname}/archive/${pkgver}.tar.gz")
md5sums=('4eef13da988edf8f91c260a3e1baeea9')

prepare() {
  mkdir build
}

build() {
  cd ${srcdir}

  sed -i 's|add_library (qjson SHARED|add_library (qjson |g' ${pkgname}-${pkgver}/src/CMakeLists.txt

  cd build
  cmake ../${pkgname}-${pkgver} \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DCMAKE_BUILD_TYPE=Release
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
