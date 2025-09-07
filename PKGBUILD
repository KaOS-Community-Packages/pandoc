pkgname=pandoc
pkgver=3.8
pkgrel=1
pkgdesc='The universal markup converter (haskell free).'
arch=('x86_64')
url='https://pandoc.org'
license=('GPL')
depends=('texlive-core')
source=("https://github.com/jgm/pandoc/releases/download/${pkgver}/pandoc-${pkgver}-linux-amd64.tar.gz"
        "https://github.com/jgm/pandoc/archive/${pkgver}.tar.gz")
sha256sums=('1a035c1f7d295c353f614461fa4bc13d703c0e865387d44341d1556d703de59a'
            '2d375526e7d26d46ebcdaf107564c8bbfd68e40a7af425906e9612889699bcf6')

package() {
    cd "${pkgname}-${pkgver}"

    # To avoid having to download over a gigabyte of haskell makedepends (400-ish for ghc, plus 750 in libs), we
    # just yoink the binary from static compiled binary distributed by pandoc:
    install -Dm755 -t "${pkgdir}/usr/bin" 'bin/*'
    cp -a share "${pkgdir}/usr/share"

    # We're still missing all the datafiles and so on. We get those from the source tarball...
    install -dm755 "${pkgdir}/usr/share/pandoc"
    cp -a data "${pkgdir}/usr/share/pandoc"

    install -Dm644 -t "${pkgdir}/usr/share/pandoc" COPYRIGHT MANUAL.txt
}
