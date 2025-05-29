pkgname=pandoc
pkgver=3.7.0.2
pkgrel=1
pkgdesc='The universal markup converter (haskell free).'
url='https://pandoc.org'
license=('GPL')
arch=('x86_64')
depends=('texlive-core')
source=("https://github.com/jgm/pandoc/releases/download/${pkgver}/pandoc-${pkgver}-linux-amd64.tar.gz"
        "https://github.com/jgm/pandoc/archive/${pkgver}.tar.gz")
sha256sums=('8f8f67fdd540b6519326b0ac49d5c55c5d5d15e43920e80a086e02c8aff83268'
            'a098c1dc8051844e3992f8396c6c947dccbc57b6ca3df2f2c47b9f7fa9f11246')

package() {
	cd "${pkgname}-${pkgver}"

	# To avoid having to download over a gigabyte of haskell makedepends (400-ish for ghc, plus 750 in libs), we
	# just yoink the binary from static compiled binary distributed by pandoc:
	install -Dm755 -t "${pkgdir}/usr/bin" bin/*
	cp -a share "${pkgdir}/usr/share"

	# We're still missing all the datafiles and so on. We get those from the source tarball...
	install -dm755 "${pkgdir}/usr/share/pandoc"
	cp -a data "${pkgdir}/usr/share/pandoc"

	install -Dm644 -t "${pkgdir}/usr/share/pandoc" COPYRIGHT MANUAL.txt
}
