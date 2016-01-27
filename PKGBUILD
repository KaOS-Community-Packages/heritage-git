pkgname=heritage-git
_pkgname=heritage
pkgver=r54.60c2eab
pkgrel=1
pkgdesc='Chakra Plasma 5 theme, a fork of Caledonia'
arch=('x86_64')
url='http://git.chakraos.org/heritage.git'
license=('Creative Commons')
depends=('plasma-framework')
makedepends=('git' 'cmake' 'extra-cmake-modules')
source=("git://git.chakraos.org/heritage.git")
sha256sums=('SKIP')

prepare() {
    pkgver
}

pkgver() {
    cd "heritage"
    printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
  mkdir -p build
  cd build
  cmake ../${_pkgname}
  make
}

package() {
  cd build
  make DESTDIR="$pkgdir" install
}