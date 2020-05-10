# Maintainer:

pkgname=st-patched
_pkgname=st
pkgver=0.8.3.r1115.3be0eea
pkgrel=1
epoch=1
pkgdesc="st with scrollback boxdraw alpha copyurl custom colors and vim keybinding + alt patches"
url='https://github.com/uttarayan21/st'
arch=('i686' 'x86_64')
license=('MIT')
options=('zipman')
depends=('libxft')
makedepends=( 'libxext' 'git')
optdepends=()
source=('git://github.com/uttarayan21/st')
sha1sums=('SKIP')

provides=("${_pkgname}")
conflicts=("${_pkgname}")

pkgver() {
	cd "${_pkgname}"
	printf "%s.r%s.%s" "$(awk '/^VERSION =/ {print $3}' config.mk)" \
		"$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

prepare() {
	cd $srcdir/${_pkgname}
}

build() {
	cd "${_pkgname}"
}

package() {
	cd "${_pkgname}"
	make PREFIX=/usr DESTDIR="${pkgdir}" install
	install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
