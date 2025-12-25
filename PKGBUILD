# Maintainer: Nero Blackstone <gf7600gs@gmail.com>

pkgname=oxen-server-bin
pkgver=0.42.2
pkgrel=1
pkgdesc="Oxen server. Oxen is a lightning fast data version control system for structured and unstructured machine learning datasets."
arch=('x86_64')
url="https://www.oxen.ai/"
license=('Apache-2.0')
source=("https://github.com/Oxen-AI/Oxen/releases/download/v${pkgver}/oxen-server-linux-x86_64.deb")
sha256sums=('8e5cdbc6993f0db947df5e7232bd1722d6032c8c532ffef483b757d93d011a41')

prepare() {
    cd "$srcdir"
    ar x oxen-server-linux-x86_64.deb
    tar -xf data.tar.*
    tar -xf control.tar.* || true
    find . -type d -exec chmod 755 {} +
    find . -type f -exec chmod 644 {} +
    chmod 755 usr/bin/* 2>/dev/null || true
    chmod 755 usr/sbin/* 2>/dev/null || true
}

package() {
    cd "$srcdir"
    cp -r usr "$pkgdir/"
}