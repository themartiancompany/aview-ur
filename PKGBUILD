# SPDX-License-Identifier: AGPL-3.0
#
# Maintainer: Truocolo <truocolo@aol.com>
# Maintainer: Pellegrino Prevete (tallero) <pellegrinoprevete@gmail.com>
# Maintainer: Jose Riha <jose1711 gmail com>
# Contributor: Johnathan Jenkins <twodopeshaggy@gmail.com>

_git="false"
_proj="aa-project"
pkgname=aview
_majver="1.3.0"
_minver="rc1"
pkgver="${_majver}_${_minver}"
_pkgver="${_majver}${_minver}"
_commit="f64b212ac7cd24f4c65064611bfd33612e74146f"
pkgrel=1
pkgdesc="an high quality ascii-art image browser"
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
makedepends=(
  'autoconf'
)
_gh="https://github.com"
_http="${_gh}"
_ns="themartiancompany"
_url="${_http}/${_ns}/${pkgname}"
_tag="${_commit}"
_tag_name="commit"
_tarname="${pkgname}-${_tag}"
if [[ "${_git}" == true ]]; then
  makedepends+=(
    "git"
  )
  _src="${_tarname}::git+${_url}#${_tag_name}=${_tag}?signed"
  _sum="SKIP"
elif [[ "${_git}" == false ]]; then
  if [[ "${_tag_name}" == 'pkgver' ]]; then
    _src="${_tarname}.tar.gz::${_url}/archive/refs/tags/${_tag}.tar.gz"
    _sum="d4f4179c6e4ce1702c5fe6af132669e8ec4d0378428f69518f2926b969663a91"
  elif [[ "${_tag_name}" == "commit" ]]; then
    _src="${_tarname}.zip::${_url}/archive/${_commit}.zip"
    _sum='985876506fc6a34026e75f30e9946beb8edab8f275b7e69b8fe0ddd82d67de9b'
  fi
fi
source=(
  "${_src}"
)
sha256sums=(
  "${_sum}"
)

build() {
  cd \
    "${_tarname}"
  autoreconf \
    -i
  ./configure \
    --prefix=/usr \
    --mandir=/usr/share/man
  make 
}

package() {
  cd \
    "${_tarname}"
  make \
    DESTDIR="${pkgdir}" \
    PREFIX="/usr" \
    MANDIR='/usr/share/man' \
    install
}

