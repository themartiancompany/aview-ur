# SPDX-License-Identifier: AGPL-3.0
#
# Maintainer: Truocolo <truocolo@aol.com>
# Maintainer: Pellegrino Prevete (tallero) <pellegrinoprevete@gmail.com>
# Maintainer: Jose Riha <jose1711 gmail com>
# Contributor: Johnathan Jenkins <twodopeshaggy@gmail.com>

_proj="aa-project"
pkgname=aview
_majver="1.3.0"
_minver="rc1"
pkgver="${_majver}_${_minver}"
_pkgver="${_majver}${_minver}"
pkgrel=3
pkgdesc="a high quality ascii-art image browser"
arch=(
  'i686'
  'x86_64'
  'arm'
  'aarch64'
  'armv7l'
  'armv6l'
  'mips'
  'pentium4'
)
url="http://${_proj}.sourceforge.net/${pkgname}/"
license=(
  'GPL'
)
depends=(
  'aalib'
)
_sf='http://downloads.sourceforge.net/sourceforge'
_http="${_sf}"
_ns="${_proj}"
_url="${_http}/${_ns}/${pkgname}-${_pkgver}.tar.gz"
source=(
  "${_url}"
)
md5sums=(
  '093f298e7787591e229b59d039c72f4d'
)

build() {
  cd \
    "${srcdir}/${pkgname}-${_majver}"
  ./configure \
    --prefix=/usr \
    --mandir=/usr/share/man
  make 
}

package() {
  cd \
    "${srcdir}/${pkgname}-${_majver}"
  make \
    DESTDIR="${pkgdir}" \
    PREFIX="/usr" \
    MANDIR='/usr/share/man' \
    install
}

