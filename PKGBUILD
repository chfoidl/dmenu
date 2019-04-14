pkgname=dmenu-chrisxf-git
_pkgname=dmenu
_pkgver=4.9
pkgver=4.9.r572.72068c9
pkgrel=1
pkgdesc="ChrisXF's customized dmenu"
url="https://github.com/ChrisXF/dmenu"
arch=("i686" "x86_64")
license=("MIT")
options=("zipman")
source=("git://github.com/ChrisXF/dmenu")
sha1sums=("SKIP")

provides=("${_pkgname}")
conflicts=("${_pkgname}")

pkgver() {
	cd "${_pkgname}"
	printf "${_pkgver}.r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

prepare() {
	cd $srcdir/${_pkgname}
}

build() {
	cd "${_pkgname}"
	make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11
}

package() {
	cd "${_pkgname}"
	make PREFIX=/usr DESTDIR="${pkgdir}" install
}
