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
_commit="8010caff18b1b7eba62b5adba91f2d88084a183e"
pkgrel=3
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
makedepends=()
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
    _sum='a6ec10857c5dfe31ac7876e6426a2d79e54f5ccd69fd694607da434b781034c5'
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

