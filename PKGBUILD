# Maintainer: Jakob Matthes <jakob.matthes@gmail.com>
pkgname=python-markdown2
pkgver=2.3.5
pkgrel=1
pkgdesc="A fast and complete implementation of Markdown in Python."
url="https://github.com/trentm/python-markdown2"
license=('MIT')
arch=('any')
depends=('python')
source=("$pkgname-$pkgver.tgz::https://github.com/trentm/python-markdown2/archive/${pkgver}.tar.gz")
md5sums=('c6d231e08fd6da1ae739708bcd1ebf1f')

package() {
  cd "$srcdir/$pkgname-$pkgver"
  python setup.py install --root="$pkgdir"
}
