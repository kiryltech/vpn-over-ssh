# $Id$
# Maintainer: Kirill Duborenko <k.duborenko@gmail.com>
pkgname=vpn-over-ssh
pkgver=0.0.4
pkgrel=1
pkgdesc="VPN over SSH"
arch=('any')
depends=('openssh')
source=(vos.conf
        vosd
        vos-start
        vos-stop
        nets)
md5sums=('cf01e4b164ef89dc953598de2ebfb57b'
         '0fd0376eb049dcd5215b4f871520e868'
         'a1c079871ecc066a27342388f66d8a1b'
         '161439a7136cb518f028c88c7c07dc85'
         '61b196ae6282de9adbecc67b16e4e23b')

build() {
    cd "${srcdir}"
    mkdir -p "${pkgdir}/usr/share/${pkgname}" || return 1
    mkdir -p "${pkgdir}/etc/${pkgname}" || return 1
    mkdir -p "${pkgdir}/etc/rc.d" || return 1
    install -m 755 vos.conf "${pkgdir}/etc/${pkgname}" || return 1
    install -m 755 vos-start "${pkgdir}/usr/share/${pkgname}" || return 1
    install -m 755 vos-stop "${pkgdir}/usr/share/${pkgname}" || return 1
    install -m 644 nets "${pkgdir}/etc/${pkgname}" || return 1
    install -m 755 vosd "${pkgdir}/etc/rc.d" || return 1
}