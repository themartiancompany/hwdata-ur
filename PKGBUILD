# SPDX-License-Identifier: AGPL-3.0
#
# Maintainer: Truocolo <truocolo@aol.com>
# Maintainer: Pellegrino Prevete (tallero) <pellegrinoprevete@gmail.com>
# Maintainer: Tobias Powalowski <tpowa@archlinux.org>
pkgname=hwdata
pkgver=0.382
pkgrel=1
pkgdesc="hardware identification databases"
makedepends=(
  'git'
)
replaces=(
  'hwids'
)
_ns="vcrhonek"
_http="https://github.com"
url="${_http}/${_ns}/${pkgname}"
license=('GPL-2.0-or-later')
arch=('any')
source=(
  "git+${url}.git#tag=v${pkgver}?signed")
validpgpkeys=(
  '3C40194FB79138CE0F78FD4919C2F062574F5403') # Vitezslav Crhonek
sha256sums=(
  'c20b03555bed7016d56adffcbe01fd2f65e3cc9fe88dc2545856512cacfa7162')

build() {
  local \
    _configure_opts=()
  _configure_opts=(
    --prefix=/usr
    --disable-blacklist
  )
  cd \
    "${pkgname}"
  ./configure \
    "${_configure_opts[@]}"
}

package() {
  local \
    _make_opts=()
  _make_opts=(
    DESTDIR="${pkgdir}"
    PREFIX="/usr"
  )
  cd \
   "${pkgname}"
  make \
    "${_make_opts[@]}" \
    install
}

# vim: ft=sh syn=sh et
