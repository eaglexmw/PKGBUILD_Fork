# $Id$
# Maintainer: Jan de Groot <jgc@archlinux.org>

pkgname=libsecret
pkgver=0.18
pkgrel=1
pkgdesc='Library for storing and retrieving passwords and other secrets.'
arch=('i686' 'x86_64')
license=('LGPL')
url="https://wiki.gnome.org/Projects/Libsecret"
depends=('glib2' 'libgcrypt')
options=('staticlibs')  # needed by binutils testsuite
makedepends=('intltool' 'docbook-xsl' 'gobject-introspection' 'vala')
optdepends=('gnome-keyring: key storage service (or use any other service implementing org.freedesktop.secrets)')
source=(http://ftp.gnome.org/pub/gnome/sources/$pkgname/$pkgver/$pkgname-$pkgver.tar.xz)
sha256sums=('0c73aa762dbd1e38ba7b03de350e23ce818cb810b0784375e95ef61e004b02e3')

build() {
  cd "$pkgname-$pkgver"
  ./configure --prefix=/usr --sysconfdir=/etc \
      --localstatedir=/var --enable-static --disable-shared
  make
}

package() {
  cd "$pkgname-$pkgver"
  make DESTDIR="$pkgdir" install
}
