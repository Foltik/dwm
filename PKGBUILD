# Maintainer: Jack Foltz <jack@foltz.io>
pkgname=dwm
pkgver=6.2
pkgrel=1
pkgdesc="Dynamic Window Manager (Foltik's Patches)"
arch=('i686' 'x86_64')
url="https://dwm.suckless.org"
license=('MIT')
depends=('libx11' 'libxft' 'libxinerama')

pkgver() {
	cd ..
	grep "VERSION = " config.mk | awk '{print $3}'
}

build() {
	cd ..
	make
}

package() {
	cd ..
	make PREFIX=/usr DESTDIR="$pkgdir" install
	install -m644 -D LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
	install -m644 -D README "$pkgdir/usr/share/doc/$pkgname/README"
}
