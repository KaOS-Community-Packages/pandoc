pkgname=pandoc
pkgver=2.11.3.2
pkgrel=1
pkgdesc='The universal markup converter.'
arch=('x86_64')
url='https://pandoc.org/'
license=('GPLv2')
depends=()
makedepends=()
source=("https://github.com/jgm/pandoc/releases/download/2.11.3.2/pandoc-${pkgver}-linux-amd64.tar.gz")
md5sums=('49dbc470395c4c6580d107e23c79debd')

src_name="pandoc-${pkgver}"

build() {
    echo "No building is actually needed"
}

package() {
    sudo tar xvzf pandoc-${pkgver}-linux-amd64.tar.gz --strip-components 1 -C /usr/local/
}
