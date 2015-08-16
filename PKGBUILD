# Maintainer: Christian Brauner <christianvanbrauner@gmail.com>

pkgname=lxcfs
pkgver=0.6
pkgrel=1
pkgdesc="FUSE filesystem for LXC"
arch=(i686 x86_64)
url="https://linuxcontainers.org/"
license=('GPL')
depends=('lxc' 'cgmanager>=0.35-1' 'libnih')
makedepends=('help2man')
source=("https://linuxcontainers.org/downloads/lxcfs/lxcfs-$pkgver.tar.gz")
md5sums=('3fc560decfa3426b3cce0dff729d17b7')

build() {
    cd "$srcdir/$pkgname-$pkgver"
    ./configure \
        --prefix=/usr \
        --sbindir=/usr/bin \
        --localstatedir=/var
    make
}

package() {
    cd "$srcdir/$pkgname-$pkgver"
    make DESTDIR="$pkgdir/" install
}
