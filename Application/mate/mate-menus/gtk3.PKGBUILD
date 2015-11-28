# Maintainer : Martin Wimpress <code@flexion.org>

_ver=1.12
# pkgname=mate-menus
pkgbase=mate-menus
pkgver=${_ver}.0
pkgrel=1
pkgname=(${pkgbase}-gtk3)
pkgdesc="MATE menu specifications"
url="http://mate-desktop.org"
arch=('i686' 'x86_64')
license=('GPL')
depends=('glib2' 'python2')
makedepends=('gobject-introspection' 'mate-common')
groups=('mate' 'mate-gtk3')
source=("http://pub.mate-desktop.org/releases/${_ver}/${pkgbase}-${pkgver}.tar.xz")
sha1sums=('a52eacac8cd912b866c085bc4a20e866572f96d6')

if [ "$CARCH" = "x86_64" ]; then
  dstdir=mate64
elif [ "$CARCH" = "i686" ]; then
  dstdir=mate
fi


build() {
    cd "${srcdir}/${pkgbase}-${pkgver}"
    PYTHON=/usr/bin/python2 ./configure \
        --prefix=/usr/local/${dstdir}/mate_gtk+3.0 \
        --sysconfdir=/usr/local/${dstdir}/mate_gtk+3.0/etc \
        --localstatedir=/var \
        --enable-python \
        --disable-static
    make
}

package() {
    cd "${srcdir}/${pkgbase}-${pkgver}"
    make DESTDIR="${pkgdir}" install
}
