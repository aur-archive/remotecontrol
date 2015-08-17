# Maintainer: MacCyber <jonas.enge at gmail dot com>

pkgname=remotecontrol
pkgver=1.0
pkgrel=1
pkgdesc="GTK+ remotecontrol for Enigma2 Web Interface"
arch=('i686' 'x86_64')
url="http://jonasenge.no/tv-remote-control/"
license=('GPL')
depends=('gtk3')
source=("http://w166890-www.php5.dittdomene.no/div/remotecontrol-${pkgver}.tar.gz"
	'remotecontrol.desktop')
md5sums=('e6ee22741f32f92746ee879a7858ab60' 'b6466c472a7ac9460fc04dee340f3f6b')

build() {
  cd "remotecontrol-${pkgver}"
  ./configure
  make
}

package() {
  install -Dm755 "remotecontrol-${pkgver}/src/remotecontrol" "${pkgdir}/usr/bin/remotecontrol" || return 1
  install -Dm644 "remotecontrol-${pkgver}/src/remotecontrol.ui" "${pkgdir}/usr/share/remotecontrol/ui/remotecontrol.ui" || return 1
  install -Dm644 "remotecontrol-${pkgver}/src/remote.png" "${pkgdir}/usr/share/pixmaps/remotecontrol/remote.png" || return 1
  install -d ${pkgdir}/usr/share/applications/
  install -Dm644 ${srcdir}/remotecontrol.desktop ${pkgdir}/usr/share/applications/ || return 1
}
