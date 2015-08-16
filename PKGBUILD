# Maintainer: Andrea Scarpino <andrea@archlinux.org>

pkgname=ktexteditor
pkgver=4.99.0
pkgrel=1
pkgdesc='KTextEditor framework'
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/frameworks/ktexteditor'
license=('LGPL')
depends=('kparts')
makedepends=('extra-cmake-modules')
groups=('kf5')
source=("http://download.kde.org/unstable/frameworks/${pkgver}/${pkgname}-${pkgver}.tar.xz")
md5sums=('a7c18d98826c0d8f90bc26579e9d8f4e')

prepare() {
  mkdir -p build
}

build() {
  export XDG_DATA_DIRS="/opt/kf5/share:$XDG_DATA_DIRS"

  cd build
  cmake ../${pkgname}-${pkgver} \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/opt/kf5 \
    -DLIB_INSTALL_DIR=lib \
    -DBUILD_TESTING=OFF
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
