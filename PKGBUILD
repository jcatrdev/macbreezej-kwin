# Maintainer: jcatrdev@gmail.com

pkgname=macbreezej-kwin-decoration-git
_gitname="macbreezej-kwin"
pkgver=1.1
pkgrel=1
pkgdesc="MacOS-like kwin decoration for KDE Plasma"
arch=('x86_64')
url="https://github.com/jcatrdev/macbreezej-kwin"
license=('GPLv3')
depends=('kwin')
makedepends=('git' 'cmake' 'extra-cmake-modules')
source=("git+${url}.git")
sha256sums=('SKIP')

build() {
    cd ${srcdir}/${_gitname}

    mkdir build && cd build
    cmake ..  \
            -DCMAKE_INSTALL_PREFIX=/usr \
            -DCMAKE_BUILD_TYPE=Release \
            -DKDE_INSTALL_LIBDIR=lib \
            -DBUILD_TESTING=OFF \
            -DKDE_INSTALL_USE_QT_SYS_PATHS=ON
}

package() {
    make -C ${srcdir}/${_gitname}/build DESTDIR="$pkgdir" install
}