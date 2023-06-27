pkgname=itec-calamares
pkgver=3.2.62
pkgrel=1
pkgdesc="Distribution-Independent Installer Framework"
arch=('x86_64')
url="https://github.com/calamares/calamares"
license=('GPL')
makedepends=('cmake' 'extra-cmake-modules' 'kpmcore' 'boost-libs' 'yaml-cpp')
depends=('qt5-svg' 'qt5-webengine' 'yaml-cpp' 'networkmanager' 'boost' 'upower'
         'kcoreaddons' 'kconfig' 'ki18n' 'kservice' 'kwidgetsaddons' 'kpmcore'
         'squashfs-tools' 'rsync' 'cryptsetup' 'qt5-xmlpatterns' 'doxygen'
         'dmidecode' 'gptfdisk' 'hwinfo' 'kparts' 'polkit-qt5' 'python' 'qt5ct'
         'solid' 'qt5-tools')
provides=("${pkgname}-${pkgver}")
source=("${url}/releases/download/v${pkgver}/${pkgname}-${pkgver}.tar.gz")
sha256sums=('7591b9b60738bdba7b9de2b8da5462ab21006db06a006f0dd21ac5b832711dd2')

build() {
           mkdir -p ${srcdir}/${pkgname}-${pkgver}/build
           cd ${srcdir}/${pkgname}-${pkgver}/build
           cmake -DCMAKE_BUILD_TYPE=Release -DWITH_PYTHONQT=ON ..
           make -j$(nproc)
}

package() {
           cd ${srcdir}/${pkgname}-${pkgver}/build
           make DESTDIR=${pkgdir} install
}
