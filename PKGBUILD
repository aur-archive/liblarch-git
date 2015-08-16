# Contributor: Francois Boulogne <fboulogne at april dot org>
# Maintainer: Francois Boulogne <fboulogne at april dot org>
pkgname=liblarch-git
pkgver=20120219
pkgrel=2
pkgdesc="Python library to easily handle data structure, with a GTK binding"
arch=('i686' 'x86_64')
url="https://live.gnome.org/liblarch"
license=('LGPL3')
depends=('python2')
optdepends=()
makedepends=('git' 'python2')
provides=()
conflicts=()
source=()
md5sums=()

_gitroot="git://github.com/ploum/liblarch.git"
_gitname="liblarch"

build() {

  cd "$srcdir"
  msg "Connecting to GIT server...."

  if [ -d $_gitname ] ; then
    cd $_gitname && git pull origin
    msg "The local files are updated."
  else
    git clone $_gitroot $_gitname
  fi

  msg "GIT checkout done or server timeout"
  msg "Starting make..."

  rm -rf "$srcdir/$_gitname-build"
  git clone "$srcdir/$_gitname" "$srcdir/$_gitname-build"
  cd "$srcdir/$_gitname-build"

  python2 setup.py install --root=${pkgdir}

}
# vim:set ts=2 sw=2 et:

