# Maintainer: 
_hkgname=yeganesh
pkgname=yeganesh
pkgver=2.5
pkgrel=2
pkgdesc="dmenu with a sense of history"
url="http://hackage.haskell.org/package/${_hkgname}"
license=('custom:BSD3')
arch=('i686' 'x86_64')
makedepends=('ghc' 'haskell-strict>=0.3' 'haskell-xdg-basedir>=0.2')
depends=('dmenu')
options=('strip')
md5sums=('1f64542082d61b9004bc42f80ce9ebac')
source=(http://hackage.haskell.org/packages/archive/${_hkgname}/${pkgver}/${_hkgname}-${pkgver}.tar.gz)
build() {
    cd ${srcdir}/${_hkgname}-${pkgver}
    runhaskell Setup configure --prefix=/usr --docdir=/usr/share/doc/${pkgname} -O
    runhaskell Setup build
}
package() {
    cd ${srcdir}/${_hkgname}-${pkgver}
    runhaskell Setup copy --destdir=${pkgdir}
    install -D -m644 LICENSE ${pkgdir}/usr/share/licenses/${pkgname}/LICENSE
    rm -f ${pkgdir}/usr/share/doc/${pkgname}/LICENSE
}
# vim:set ts=2 sw=2 et:
