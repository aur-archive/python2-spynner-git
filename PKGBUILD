# Maintainer: Allen Li <darkfeline@abagofapples.com>

pkgname=python2-spynner-git
pkgver=20130105
pkgrel=1
pkgdesc="Programmatic web browsing module with AJAX support for Python 2"
arch=('any')
url="http://pypi.python.org/pypi/spynner/"
license=('GPL3')
depends=('python2' 'libxml2' 'pyqt')
makedepends=('git' 'python2-setuptools_git')

_gitname=spynner
_gitroot='git://github.com/makinacorpus/spynner.git'

build() {
    cd "$srcdir"
    msg "Connecting to GIT server..."
    if [ -d $_gitname ] ; then
        cd $_gitname && git pull origin
        msg "The local files are updated."
    else
        git clone --depth=1 $_gitroot
    fi
    msg "GIT checkout done or server timeout"

    cd $srcdir/spynner
    python2 setup.py build
}

package() {
    cd "$srcdir/spynner"
    python2 setup.py install --root="$pkgdir"
}
