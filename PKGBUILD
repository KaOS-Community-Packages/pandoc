pkgname=pandoc
pkgver=3.1.6
pkgrel=1
pkgdesc='The universal markup converter (haskell free).'
url='https://pandoc.org'
license=('GPL')
arch=('x86_64')
depends=('texlive-core')
source=("https://github.com/jgm/pandoc/releases/download/${pkgver}/pandoc-${pkgver}-linux-amd64.tar.gz"
        "https://github.com/jgm/pandoc/archive/${pkgver}.tar.gz")
sha256sums=('6eec0e0c85e97c90a02b9184c993d4bd848426fb3d7452ddc0d6014368c5e3fd'
            '3194ab5b37ab1b80bb0be023753fbc78207df5f093caeb2ac6edb5dc0d5e704b')

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
