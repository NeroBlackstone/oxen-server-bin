# Maintainer: Nero Blackstone <gf7600gs@gmail.com>

pkgname=oxen-server-bin
pkgver=0.26.0
pkgrel=1
pkgdesc="Oxen server. Oxen is a lightning fast data version control system for structured and unstructured machine learning datasets."
arch=('x86_64')
url="https://www.oxen.ai/"
license=('Apache-2.0')
source=("https://github.com/Oxen-AI/Oxen/releases/download/v${pkgver}/oxen-server-ubuntu-latest.deb")
sha256sums=('9cbc6eb8e4314dd088b4b4a16853ce436e3a1edc47abd6ce1203ad7572d9f73b')

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
