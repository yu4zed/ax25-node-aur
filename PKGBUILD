# Maintaner: Wijnand Modderman-Lenstra <maze@pyth0n.org>
# Contributor: Gordon JC Pearce <gordon@gjcp.net>
pkgname=ax25-node
pkgver=0.3.2
pkgrel=3
pkgdesc="AX25 node software"
arch=(i686 x86_64)
url="http://tldp.org/HOWTO/AX25-HOWTO/x1688.html"
license=('GPL')
depends=('libax25')
makedepends=('linux-headers' 'patch' 'make' 'gcc')
optdepends=('ax25-tools: hamradio modem support'
            'soundmodem: software packet radio modem')
source=(
  http://ftp.de.debian.org/debian/pool/main/n/node/node_0.3.2.orig.tar.gz
  node.patch
)
sha1sums=('810c950bd33a7f719a93be6c074ca2500c047af4'
          '384f6c798fa2d9d8b8bf9ab6cd589534bc212fb8')
sha256sums=('41879021150084e2eb923f414dbd1082af1d46e10313a52137c9ce1e7eff64d5'
            '3e85c5972ef0754d82287ea6a3cf08679704b4ed66b180d57a23f9786bbb44a6')

build() {
  cd "$srcdir/node-$pkgver"
  patch -p1 < $srcdir/node.patch
  ./configure 
  make || return 1
}

package() {
  cd "$srcdir/node-$pkgver"
  make DESTDIR="$pkgdir/" install
}

