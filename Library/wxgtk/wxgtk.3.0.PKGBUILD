# $Id$
# Maintainer: Eric Bélanger <eric@archlinux.org>

pkgname=wxgtk
pkgver=3.0.0
pkgrel=2
pkgdesc="GTK+ implementation of wxWidgets API for GUI"
arch=('i686' 'x86_64')
url="http://wxwidgets.org"
license=('custom:wxWindows')
#depends=('gtk2' 'gstreamer0.10-base')
#makedepends=('gstreamer0.10-base-plugins' 'gconf' 'webkitgtk2' 'glu')
optdepends=('webkitgtk2: for webview support')
options=('!emptydirs')
source=(http://downloads.sourceforge.net/wxwindows/wxWidgets-${pkgver}.tar.bz2)
sha1sums=('756a9c54d1f411e262f03bacb78ccef085a9880a')

build() {
  cd wxWidgets-${pkgver}
  ./configure --prefix=/usr/local --libdir=/usr/local/lib --with-gtk=2 --with-opengl --enable-unicode \
    --enable-graphics_ctx --enable-webview --enable-stl --with-regex=builtin \
    --with-libpng=sys --with-libxpm=sys --with-libjpeg=sys --with-libtiff=sys \
    --disable-precomp-headers
  make
  make -C locale allmo
}

package() {
  cd wxWidgets-${pkgver}
  make DESTDIR="${pkgdir}" install
  install -D -m644 docs/licence.txt "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
