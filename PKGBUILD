# Maintainer: Markus Pesch <markus.pesch@cryptic.systems>

pkgname=dyndns-client
pkgver=master
pkgrel=1
pkgdesc='DynDNS client'
arch=('x86_64' 'armv7h')
url=https://git.cryptic.systems/volker.raschek/dyndns-client
license=('Apache 2.0')
depends=()
makedepends=('git' 'go')
source=(
  "https://git.cryptic.systems/volker.raschek/dyndns-client/archive/${pkgver}.zip"
)
sha512sums=('SKIP')

build() {
  GOBIN=${HOME}/go/bin
  PATH=${GOBIN}:${PATH}
  make --directory ${srcdir}/dyndns-client dyndns-client VERSION=${pkgver}
}

package() {
  install -D --mode 0755 ${srcdir}/dyndns-client/dyndns-client ${pkgdir}/usr/bin/dyndns-client
  install -D --mode 0644 ${srcdir}/dyndns-client/LICENSE ${pkgdir}/usr/share/licenses/dyndns-client/LICENSE
}
