# $Id$
# Maintainer: BlackEagle <ike.devolder@gmail.com>>

pkgname=kodi-addon-audioencoder-vorbis
epoch=1
pkgver=1.1.1
pkgrel=1
pkgdesc="Vorbis Audio Encoder add-on for Kodi"
arch=('x86_64')
url='https://github.com/xbmc/audioencoder.vorbis'
license=('GPL')
groups=('kodi-addons' 'kodi-addons-audioencoder')
provides=('kodi-audioencoder-vorbis')
replaces=('kodi-audioencoder-vorbis')
depends=('kodi')
makedepends=('cmake' 'kodi-dev')
source=("$pkgname-$pkgver.tar.gz::https://github.com/xbmc/audioencoder.vorbis/archive/v$pkgver.tar.gz")
sha512sums=('6337d18b254b439d43044a52ea66589aea0e917bc598a91948ede27440563ec176e0b0af1148da8d5e67bdf1c25492db129bc4d3eb5d0d3a1f37b7918b89ecf5')

build() {
	cd "audioencoder.vorbis-$pkgver"
	cmake \
		-DCMAKE_INSTALL_PREFIX=/usr \
		-DCMAKE_BUILD_TYPE=Release \
		-DBUILD_SHARED_LIBS=1 \
		-DUSE_LTO=1
	make
}

package() {
	cd "audioencoder.vorbis-$pkgver"
	make DESTDIR="$pkgdir/" install
}

