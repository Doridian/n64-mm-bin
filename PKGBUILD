# Maintainer: Doridian <archlinux at doridian dot net>

pkgname=n64-mm-bin
pkgver=1.1.2
pkgrel=1
pkgdesc='Recompilation of Ocarina of Time for modern systems'
arch=('x86_64')
url='https://github.com/HarbourMasters/2ship2harkinian'
license=('Commercial') # As the built artifact includes the ROM or resources derived from it
makedepends=('unzip')
depends=('zlib' 'fuse2')
options=('!strip' '!debug')
_relfile="2Ship-Satoko-Charlie-Linux.zip"
source=(
    "${url}/releases/download/${pkgver}/${_relfile}"
    'baserom.z64' # Copyrighted, you have to find this yourself, make sure to check on https://2ship.equipment/
    'launch.sh'
    'n64-mm-bin.desktop'
    'logo.png'
)
sha256sums=(
    '42e4186c60f48e3748038e1932b3aeaeec9d2c944b9a502994ac8707dcff7935'
    'SKIP'
    'SKIP'
    'SKIP'
    'SKIP'
)

build() {
  cd "${srcdir}"
  unzip -o "${_relfile}"
}

package() {
  cd "${srcdir}"

  install -Dm644 logo.png "${pkgdir}/usr/share/pixmaps/n64-mm-bin.png"
  install -Dm644 n64-mm-bin.desktop "${pkgdir}/usr/share/applications/n64-mm-bin.desktop"

  install -Dm755 launch.sh "${pkgdir}/opt/n64/mm-bin/launch.sh"
  install -Dm755 2ship.appimage "${pkgdir}/opt/n64/mm-bin/2ship.appimage"
  install -Dm644 baserom.z64 "${pkgdir}/opt/n64/mm-bin/baserom.z64"
}

# vim:set ts=2 sw=2 et:
