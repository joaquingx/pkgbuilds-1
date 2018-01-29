# Maintainer: Joaquin Garmendia <joaquingc123 at gmail dot com>

pkgname=python-binarytree
pkgver=3.0.1
pkgrel=1
pkgdesc="A Python library which provides a simple API to generate, visualize, inspect and manipulate binary trees"
arch=("any")
url="https://github.com/joowani/${pkgname#python\-}"
license=('MIT')
depends=('python')
makedepends=('python-setuptools') 
checkdepends=('python-pytest')
source=("https://github.com/joowani/${pkgname#python\-}/archive/3.0.1.tar.gz")
sha256sums=('af7c683e307792c07c7698c3070af99247c17eb0143f7b81fcf085d8e638b6f9')
#options=('!strip')

build() {
	cd ${pkgname#python\-}-${pkgver}
	python setup.py build
}

package() {
	cd "${srcdir}/${pkgname#python\-}-${pkgver}"
	python setup.py install --root="${pkgdir}" --optimize=1 --skip-build
	install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}

check() {
	cd "${srcdir}/${pkgname#python\-}"-${pkgver}
	python tests.py
}
