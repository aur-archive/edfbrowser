# Maintainer: speps <speps at aur dot archlinux dot org>

pkgname=edfbrowser
pkgver=1.53
pkgrel=1
pkgdesc="A viewer and toolbox for timeseries storage files like EEG, EMG, ECG, BioImpedance, etc."
arch=(i686 x86_64)
url="http://www.teuniz.net/edfbrowser/"
license=('GPL')
depends=('qt4')
install="$pkgname.install"
source=("${url}${pkgname}_${pkgver/.}_source.tar.gz"
	"$pkgname.desktop")
md5sums=('e4f8c6f2ba50152e93c956a3bb8b4afc'
         '15ee52eb704bf15498326a8ab29e2c91')

build() {
  cd ${pkgname}_${pkgver/.}_source
  qmake-qt4 && make -j4
}

package() {
  cd ${pkgname}_${pkgver/.}_source

  # bin
  install -Dm755 $pkgname \
    "$pkgdir/usr/bin/$pkgname"

  # desktop
  install -Dm644 ../$pkgname.desktop \
    "$pkgdir/usr/share/applications/$pkgname.desktop"

  # icon
  install -Dm644 images/edf.png \
    "$pkgdir/usr/share/pixmaps/$pkgname.png"

  # doc
  install -d "$pkgdir/usr/share/doc/$pkgname"
  install -Dm644 doc/* "$pkgdir/usr/share/doc/$pkgname"
}

# vim:set ts=2 sw=2 et:
