# Maintainer: Drew S. Ortega <orvyx@protonmail.com>
pkgname=Brim
pkgver=0.25.0_prerelease_8d26e6e4.0
pkgrel=1
pkgdesc="Desktop application to efficiently search large packet captures and Zeek logs."
arch=('x86_64')
url="https://www.brimsecurity.com/download/"
license=('custom')
depends=('gtk3' 'libnotify' 'nss' 'libxss' 'libxtst' 'xdg-utils' 'at-spi2-core' 'glib2')
optdepends=('lsb-release' 'libgnome-keyring' 'pulseaudio')
source=("https://storage.googleapis.com/brimsec-releases/brim/${pkgver//_/-}/linux/$pkgname-${pkgver//_/-}.deb"
"https://raw.githubusercontent.com/brimdata/brim/main/LICENSE.txt"
)
noextract=("$pkgname-${pkgver//_/-}.deb")
sha256sums=('530d95c2f5dbba0a474012d75f920316516e032f9b298a4a973d0bc15df8d2b2' 'ebc2978c53b0f92bc5e540c07b3d8d864295dd5a448596b2f1131be6ee2edfca')

package() {
	# extract to pkgdir
	bsdtar -O -xf "$pkgname-${pkgver//_/-}.deb" data.tar.xz | bsdtar -C "${pkgdir}" -xJf -

	# remove debian-specific files
	rm -rf "${pkgdir}/usr/share/lintian"

	# install LICENSE.txt
	install -dm755 "${pkgdir}/usr/share/licenses/${pkgname}"	
	install "LICENSE.txt" "${pkgdir}/usr/share/licenses/${pkgname}"
}
