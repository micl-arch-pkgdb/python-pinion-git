# Maintainer: Michael W. Lloyd <micl_dev@protonmail.com>
# Contributor: yaqwsx 
pkgname=python-pinion
_pkgname=Pinion
pkgver=v0.3.0.r0.gdfb53dd  # Update this according to the latest version
pkgrel=1
pkgdesc="eenis?"
arch=('any')
url="https://github.com/yaqwsx/Pinion"
license=('MIT')  # Update this according to the package's license
depends=( 'python' 'python-pcbnewTransition' 'python-pcbdraw' 'python-svgpathtools' 'python-ruamel-yaml' )
makedepends=('git' 'python-setuptools' 'python-wheel')
provides=('python-pinion')
conflicts=('python-pinion')
source=("git+https://github.com/yaqwsx/Pinion.git")
md5sums=('SKIP')

pkgver() {
  cd "${srcdir}/${_pkgname}"
  # Use the git tag as the version number or any other versioning scheme you prefer
  git describe --long --tags | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

build() {
  cd "${srcdir}/${_pkgname}"
  python3 setup.py sdist bdist_wheel
}

package() {
  cd "${srcdir}/${_pkgname}"
  install -Dm644 "LICENSE" "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"  # Update this line if the package has a different license file
  python3 -m pip install --no-deps --ignore-installed --root="${pkgdir}" --no-warn-script-location dist/*.whl
}
