# Maintainer: koraynilay <koray.fra@gmail.com>
pkgname=scrnsvr
pkgver=1
pkgrel=9
pkgdesc="Yet Another X Screensaver/locker"
arch=('x86_64')
url="https://github.com/koraynilay/scrnsvr"
license=('WTFPL')
depends=('pulseaudio' 'grep' 'procps-ng' 'libxss')
makedepends=('git' 'gcc')
conflicts=('scrnsvr-bin')
source=("$pkgname-$pkgver::git+https://github.com/koraynilay/scrnsvr")
optdepends=('dunst: dunstify for notifications' 'libnotify: for notifications')
install="scrnsvr.install"
md5sums=("SKIP")

build() {
	cd "$srcdir/$pkgname-$pkgver"
	gcc -g -O0 -Wl,-z,relro,-z,now scrnsvr.c -o scrnsvr -lXss -lX11 -lpthread
}

package() {
	cd "$pkgname-$pkgver"
	install -Dm0755 scrnsvr "$pkgdir/usr/bin/$pkgname"
	install -Dm0644 LICENSE "$pkgdir/usr/share/licenses/scrnsvr/LICENSE"
	install -Dm0644 RETURN_CODES.txt "$pkgdir/usr/share/scrnsvr/RETURN_CODES.txt"
	install -Dm0644 scrnsvr.ini.example "$pkgdir/usr/lib/systemd/user/scrnsvr.ini.example"
	install -Dm0644 scrnsvr.service "$pkgdir/usr/lib/systemd/user/scrnsvr.service"
}
