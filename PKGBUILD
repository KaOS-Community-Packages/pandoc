pkgname=pandoc
pkgver=3.1.4
pkgrel=1
pkgdesc='The universal markup converter (haskell free).'
url='https://pandoc.org'
license=('GPL')
arch=('x86_64')
depends=('texlive-core')
source=("https://github.com/jgm/pandoc/releases/download/${pkgver}/pandoc-${pkgver}-linux-amd64.tar.gz"
        "https://github.com/jgm/pandoc/archive/${pkgver}.tar.gz")
sha256sums=('0446e131e121622c68b162e37d1c2f7645c1823197b5e3bf4c0b2627fcb2e149'
            'ff6a72b125e78b038e2e410028981301a000162f7e7693888b7c131e0f3ee6e8')

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
