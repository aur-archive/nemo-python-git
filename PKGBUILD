# Maintainer: xzy3186 <xzy3186@gmail.com>

_pkgname=nemo-python
pkgname=${_pkgname}-git
pkgver=2.2.x
pkgrel=1
pkgdesc="Unstable bindings for the nemo extension library"
arch=('i686' 'x86_64')
url="https://github.com/linuxmint/nemo-extensions"
license=('custom:CC-BY-ND-3' 'GPL')
depends=('nemo' 'python2' 'python2-gobject2')
makedepends=('git' 'gnome-common' 'gtk-doc')

_gitroot=git://github.com/linuxmint/nemo-extensions.git
_gitname=nemo-extensions

source=("$_gitroot")
md5sums=('SKIP')

pkgver() {
   cd "$srcdir/$_gitname"
   git describe --always | sed 's|-|.|g'
}

build() {

  cd ${srcdir}/nemo-extensions/${_pkgname}
  ./autogen.sh --prefix=/usr --sysconfdir=/etc --localstatedir=/var \
     --disable-static \
     PYTHON=python2

  make
}

package() {
  cd ${srcdir}/nemo-extensions/${_pkgname}
  make DESTDIR="${pkgdir}" install
}
