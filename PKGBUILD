pkgname=pandoc
pkgver=2.14
pkgrel=1
pkgdesc='The universal markup converter.'
arch=('x86_64')
url='https://pandoc.org/'
license=('GPLv2')
depends=()
makedepends=()
source=("https://github.com/jgm/pandoc/releases/download/${pkgver}/pandoc-${pkgver}-linux-amd64.tar.gz")
noextract=("pandoc-${pkgver}-linux-amd64.tar.gz")
md5sums=('bd7414d9e3396aa34d80b2d417b08d5d')

src_name="pandoc-${pkgver}"

package() {
    mkdir -p ${pkgdir}/usr/local
    tar xvzf pandoc-${pkgver}-linux-amd64.tar.gz --strip-components 1 -C "${pkgdir}/usr/local/"
}
