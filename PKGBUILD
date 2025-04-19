# Maintainer: Nero Blackstone <gf7600gs@gmail.com>

pkgname=oxen-server-bin
pkgver=0.33.1
pkgrel=1
pkgdesc="Oxen server. Oxen is a lightning fast data version control system for structured and unstructured machine learning datasets."
arch=('x86_64')
url="https://www.oxen.ai/"
license=('Apache-2.0')
source=("https://github.com/Oxen-AI/Oxen/releases/download/v${pkgver}/oxen-server-ubuntu-latest.deb")
sha256sums=('f0841b2855d59f91362e49f083ede7e6a8695e4cf7d14848b9ceb25190bed0c5')

prepare() {
    mkdir -p "$srcdir/$pkgname-$pkgver"
    cd "$srcdir/$pkgname-$pkgver"
    ar x "$srcdir/oxen-server-ubuntu-latest.deb"
    tar --use-compress-program=unzstd -xvf data.tar.gz
}

package() {
    cd "$srcdir/$pkgname-$pkgver"
    
    install -dm755 "$pkgdir/usr/bin"
    cp -r usr/bin/* "$pkgdir/usr/bin/"
    
    install -dm755 "$pkgdir/usr/share"
    cp -r usr/share/* "$pkgdir/usr/share/"
}
