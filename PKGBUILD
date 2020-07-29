# vim:set ft=sh et:
# Maintainer : BlackEagle < ike DOT devolder AT gmail DOT com >

_pkgname=tuxedo-cc-wmi
pkgname=$_pkgname-bede-lts
pkgver=0.1.4
_current_linux_version=5.4.54
_next_linux_version=5.5
pkgrel=3
pkgdesc="WMI method control for TUXEDO laptops for linux-bede-lts"
arch=('x86_64')
url="https://github.com/tuxedocomputers/tuxedo-cc-wmi"
makedepends=(
    "linux-bede-lts>=$_current_linux_version"
    "linux-bede-lts-headers>=$_current_linux_version"
    "linux-bede-lts<$_next_linux_version"
    "linux-bede-lts-headers<$_next_linux_version"
    "tuxedo-cc-wmi-dkms=$pkgver"
)
provides=('tuxedo-cc-wmi')
license=('GPL3')
source=()

package() {
	depends=(
        "linux-bede-lts>=$_current_linux_version"
        "linux-bede-lts<$_next_linux_version"
    )

    local kernver=$(</usr/src/linux-bede-lts/version)
    local extradir="/usr/lib/modules/$kernver/extramodules"
    install -dm755 "${pkgdir}${extradir}/$_pkgname"
    cp -a "/var/lib/dkms/$_pkgname/kernel-$kernver-x86_64/module"/* \
        "${pkgdir}${extradir}/$_pkgname/"
}






