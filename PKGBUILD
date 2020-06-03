# Maintainer: koraynilay <koray.fra@gmail.com>
pkgname=scrnsvr
pkgver=1.0
pkgrel=1
pkgdesc="X Screensaver/locker"
arch=('x86_64')
url="https://github.com/koraynilay/scrnsvr"
license=('custom')
depends=('pulseaudio' 'wmctrl' 'grep' 'procps-ng')
source=("$pkgname-$pkgver::git+https://github.com/koraynilay/scrnsvr")
optdepends=('dunst: dunstify for notifications' 'notify-send: for notifications')
md5sums=("SKIP")

build() {
	cd "$srcdir/$pkgname-$pkgver"
	gcc scrnsvr.c -o scrnsvr -lXss -lX11 -lpthread
}

package() {
	cd "$pkgname-$pkgver"
	install -Dm0755 scrnsvr "$pkgdir/usr/bin/$pkgname"
}
