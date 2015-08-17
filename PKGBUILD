# Maintainer: Jameson Pugh <imntreal@gmail.com>
# Contributor: Daniel Kirchner <daniel@ekpyron.rog>
# Contributor: Gustavo Alvarez <sl1pkn07@gmail.com>
# Contributor: Chase Geigle <sky@skystrife.com>

pkgname=sdl2
pkgver=2.0.0
pkgrel=7
pkgdesc="A library for portable low-level access to a video framebuffer, audio output, mouse, and keyboard (Version 2.0)."
arch=('i686' 'x86_64')
url="http://www.libsdl.org"
license=('MIT')
makedepends=('cmake')
depends=('sh')
conflicts=('sdl2-hg')
source=("http://www.libsdl.org/tmp/release/SDL2-${pkgver}.tar.gz")
sha256sums=('SKIP')

prepare() {
  mkdir -p "${srcdir}/SDL2-${pkgver}/build"
}

build() {
  cd "${srcdir}/SDL2-${pkgver}/build"
  cmake .. -DCMAKE_INSTALL_PREFIX=/usr -DSDL_STATIC=OFF
  make
}

package() {
  cd "${srcdir}/SDL2-${pkgver}/build"
  make DESTDIR="${pkgdir}/" install
  install -Dm644 ../COPYING.txt "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"

  install -Dm644 ../sdl2.m4 "${pkgdir}/usr/share/aclocal/sdl2.m4"
}
