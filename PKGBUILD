pkgname=pandoc
pkgver=3.1.7
pkgrel=1
pkgdesc='The universal markup converter (haskell free).'
url='https://pandoc.org'
license=('GPL')
arch=('x86_64')
depends=('texlive-core')
source=("https://github.com/jgm/pandoc/releases/download/${pkgver}/pandoc-${pkgver}-linux-amd64.tar.gz"
        "https://github.com/jgm/pandoc/archive/${pkgver}.tar.gz")
sha256sums=('63237f1a333371cab324a8780dd13455386d68aa92b4289175611cfdad1f302c'
            'f0cc7f6ce5a090c2389659a76e88788ae788f175343e01666c37b7e42ac0a9ff')

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
