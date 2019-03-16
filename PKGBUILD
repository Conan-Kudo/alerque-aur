# Maintainer: Gabriel Magno <gabrielmagno1@gmail.com>
# Contributor: Michał Pałubicki <maln0ir@gmx.com>

_pkgname=agate-dbf
pkgname=python-$_pkgname
pkgver=0.2.1
pkgrel=1
pkgdesc="Adds read support for dbf files to agate"
arch=('any')
url="http://agate-dbf.readthedocs.org/"
license=('MIT')
depends=(
    'python'
    'python-agate>=1.5.0'
    'python-dbfread>=2.0.5'
    'python-sphinx_rtd_theme>=0.1.6'
  )
makedepends=(
    'python-setuptools'
    'python-sphinx>=1.2.2'
  )
source=("https://github.com/wireservice/agate-dbf/archive/${pkgver}.tar.gz")
sha256sums=('de6ec33fb3e033c4c74376997265e57fbd585195acf0386e28550209bae94a08')

package() {
  cd "$srcdir/$_pkgname-$pkgver"
  python setup.py install --root="$pkgdir/" --optimize=1

  python setup.py build_sphinx
  mkdir -p "$pkgdir/usr/share/doc"
  cp -rv "$srcdir/$_pkgname-$pkgver/build/sphinx/html" "$pkgdir/usr/share/doc/$_pkgname"

  _rtd_theme_path="$(python -c 'import sphinx_rtd_theme; print(sphinx_rtd_theme.get_html_theme_path())')"
  rm -rvf "$pkgdir/usr/share/doc/$_pkgname/_static"
  ln -svf "$_rtd_theme_path/sphinx_rtd_theme/static" "$pkgdir/usr/share/doc/$_pkgname/_static"
}

check() {
    cd "$srcdir/$_pkgname-$pkgver"
    python setup.py test --test-suite=tests
}

# vim:set ts=2 sw=2 et:
