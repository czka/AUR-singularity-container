# Maintainer: Maciej Sieczka <msieczka at sieczka dot org>

pkgname='singularity-container'
pkgver='3.7.1'
pkgrel='2'
pkgdesc='Container platform focused on supporting "Mobility of Compute".'
arch=('i686' 'x86_64')
url='https://www.sylabs.io/singularity/'
license=('BSD')
makedepends=('go')
depends=('squashfs-tools' 'libseccomp')
source=("https://github.com/sylabs/singularity/releases/download/v${pkgver}/singularity-${pkgver}.tar.gz")
sha256sums=('82d2c65063560195ec34551931be3c325b95e8e2009e92755fd7daad346e083c')

build() {
  cd "singularity"
  ./mconfig --prefix=/usr --sysconfdir=/etc --localstatedir=/var --sbindir=/usr/bin -V ${pkgver}
  cd builddir
  make
}

package() {
  cd "singularity/builddir"
  make DESTDIR="${pkgdir}" install man
}
