pkgname=pandoc
pkgver=3.7.0.1
pkgrel=1
pkgdesc='The universal markup converter (haskell free).'
url='https://pandoc.org'
license=('GPL')
arch=('x86_64')
depends=('texlive-core')
source=("https://github.com/jgm/pandoc/releases/download/${pkgver}/pandoc-${pkgver}-linux-amd64.tar.gz"
        "https://github.com/jgm/pandoc/archive/${pkgver}.tar.gz")
sha256sums=('73824100c139dfa5917a45974513d6dbdaf03658424000ddef8c4b0cde7cce88'
            'f116324c77ce0aa16ed09d56557088260fb79137f19eea654c86fba06badb3ac')

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
