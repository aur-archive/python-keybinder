# Maintainer: Can Celasun <dcelasun[at]gmail[dot]com>
# Contributor: Asa Marco <marcoasa90@gmail.com>
# Contributor: SpepS <dreamspepser at yahoo dot it>

pkgname=python-keybinder
pkgver=0.2.2
pkgrel=5
pkgdesc="Python bindings to libkeybinder, a library for registering global keyboard shortcuts"
arch=(i686 x86_64)
url="http://kaizer.se/wiki/keybinder/"
license=('GPL')
depends=('libkeybinder' 'pygtk')
conflicts=('keybinder')
options=('!libtool')
source=(http://kaizer.se/publicfiles/keybinder/keybinder-$pkgver.tar.gz)
md5sums=('b4ccd4bd19f3ae3f0ab2cbda11fcd3ac')

build() {
  cd "$srcdir/keybinder-$pkgver"

  export PYTHON="/usr/bin/python2"

  ./configure \
	--prefix=/usr \
	--enable-python \
	--disable-lua

  make
}

package() {
  cd "$srcdir/keybinder-$pkgver/$pkgname"

  make DESTDIR="$pkgdir/" install
}
