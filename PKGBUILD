# Contributor: Kevin Piche <kevin@archlinux.org>
# Contributor: Sarah Hay <sarahhay@mb.sympatico.ca>

pkgname=gift-gnutella
pkgver=0.0.11
pkgrel=3
pkgdesc="GiFT's Gnutella plugin."
arch=(i686 x86_64)
url="http://gift.sourceforge.net"
license=('GPL')
depends=('gift' 'zlib')
options=(!libtool)
source=(http://downloads.sourceforge.net/sourceforge/gift/${pkgname}-${pkgver}.tar.bz2)
md5sums=('279c7dc0121b3b7e209b09c98d10f17f')

build() {
  cd ${srcdir}/${pkgname}-${pkgver}
  touch NEWS AUTHORS
  ./configure --prefix=/usr|| return 1
  make || return 1
  make DESTDIR=${pkgdir} install || return 1
  install -D -m644 data/Gnutella.conf ${pkgdir}/usr/share/giFT/Gnutella/Gnutella.conf
  install -D -m644 data/hostiles.txt ${pkgdir}/usr/share/giFT/Gnutella/hostiles.txt
}
