# Maintainer: archtux <antonio dot arias99999 at gmail dot com>

pkgname=kdeplasma-applets-distrowatcher
pkgver=0.11.1
pkgrel=1
pkgdesc="Plasmoid that displays the latest releases of Linux distributions and packages, as published in Distrowatch.com."
arch=('i686' 'x86_64')
url="http://kde-apps.org/content/show.php/Distro+Watcher+?content=157314"
license=('GPL3')
depends=('kdelibs>4.10')
makedepends=('automoc4' 'cmake')
source=(http://kde-apps.org/CONTENT/content-files/157314-distrowatcher-$pkgver.tar.gz)
md5sums=('040534331643d9e126d88e31cec631e1')

prepare() {
  cd $srcdir/distrowatcher-$pkgver
  mkdir build
  cd build
  export QT_SELECT=4
  cmake -DQT_QMAKE_EXECUTABLE=/usr/bin/qmake-qt4 -DCMAKE_INSTALL_PREFIX=`kde4-config --prefix` ..
}

build() {
  cd $srcdir/distrowatcher-$pkgver/build
  make
}

package() {
  cd $srcdir/distrowatcher-$pkgver/build
  make DESTDIR=$pkgdir install
}