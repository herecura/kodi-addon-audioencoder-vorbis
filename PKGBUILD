# Maintainer: BlackEagle <ike.devolder@gmail.com>>

pkgname=kodi-addon-audioencoder-vorbis
epoch=1
pkgver=2.0.2
_codename=Leia
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
source=("$pkgname-$pkgver.tar.gz::https://github.com/xbmc/audioencoder.vorbis/archive/v$pkgver-$_codename.tar.gz")
sha512sums=('9f6262cbd39735b6492e9d5a4f2fb0e0277d32428fab2aca463d104e7f49e68ce922c4ee633a830eb855aa42a7cff6392a98637bcc09e5dc19ee57807af02dd2')

build() {
    cd "audioencoder.vorbis-$pkgver-$_codename"
    cmake \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -DBUILD_SHARED_LIBS=1 \
        -DUSE_LTO=1 \
        .
    make
}

package() {
    cd "audioencoder.vorbis-$pkgver-$_codename"
    make DESTDIR="$pkgdir/" install
}

