# Maintainer: koraynilay <koray.fra@gmail.com>
pkgname=scrnsvr
pkgver=1.0
pkgrel=1
epoch=
pkgdesc="X Screensaver/locker"
arch=('x86_64')
url="https://github.com/koraynilay/scrnsvr"
license=('custom')
depends=('pulseaudio' 'wmctrl' 'grep' 'procps-ng')
makedepends=()
source=("$pkgname-$pkgver::git+https://github.com/koraynilay/scrnsvr")
optdepends=('dunst' 'notify-send')
md5sums=("SKIP")

build() {
	cd "$srcdir/$pkgname-$pkgver"
	gcc scrnsvr.c -o scrnsvr -lXss -lX11 -lpthread
}

package() {
	cd "$pkgname-$pkgver"
	echo $pkgdir
	install -Dm0755 scrnsvr "$pkgdir/usr/bin/$pkgname"
	echo "'dunst' and 'notify-send' packages are used for the notification before saving (can be disabled with the -n switch)"
}
