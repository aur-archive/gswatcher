#Maintainer: Alexander AB <lxndr87i@gmail.com>

pkgname=gswatcher
pkgver=1.5.1
pkgrel=1
pkgdesc="A simple game server browser and an administrative tool"
arch=('i686' 'x86_64')
url="http://gswatcher.sourceforge.net"
license=('GPLv3')
depends=('gtk3' 'geoip' 'gsettings-desktop-schemas')
makedepends=('cmake')
optdepends=('libnotify: GNOME integration'
			'gstreamer: sound notifications'
			'mplayer: sound notifications'
			'vlc: sound notifications')
source=("http://gswatcher.sourceforge.net/releases/$pkgname-$pkgver.tar.xz")
md5sums=('5a66d8437ef475aca2978ce34c9ec05e')


build() {
	cd $srcdir/$pkgname-$pkgver
	cmake -DCMAKE_BUILD_TYPE=Release \
		-DGSWATCHER_BUILD_TESTS=OFF \
		-DCMAKE_INSTALL_PREFIX=/usr \
		CMakeLists.txt
	make
}


package() {
	cd $srcdir/$pkgname-$pkgver
	make DESTDIR="$pkgdir" install
}
