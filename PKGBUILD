# Maintainer: Gabby <28601 dash gabby at users dot noreply dot gitlab dot freedesktop dot org>
# Maintainer: Julien <aur dot arch at fastmail dot com>
pkgname=snapper-rollback-efi
pkgver=1.2
pkgrel=1
pkgdesc='Script to rollback snapper snapshots as described here https://wiki.archlinux.org/index.php/Snapper#Suggested_filesystem_layout'
arch=('any')
license=('GPL3')
url='https://github.com/bkmo/snapper-rollback-efi'
depends=('coreutils' 'python' 'btrfs-progs' 'rsync')
optdepends=('snapper')
provides=('snapper-rollback')
conflicts=('rollback-git' 'snapper-rollback''snapper-rollback-boot')
replaces=('rollback-git' 'snapper-rollback''snapper-rollback-boot')
backup=(etc/snapper-rollback.conf)
source=("$url/archive/refs/tags/$pkgver.tar.gz")
sha256sums=('SKIP')

    package() {
    cd $pkgname-$pkgver
    install -Dm644  "zz1-efi-backup.hook" -t "$pkgdir/usr/share/libalpm/hooks/"
    install -Dm644  "snapper-rollback.conf" -t "$pkgdir/etc/"
    install -Dm755  "snapper-rollback" -t "$pkgdir/usr/bin/"
    install -Dm755  "rollback" -t "$pkgdir/usr/bin/"
    install -Dm755  "rollback-root" -t "$pkgdir/usr/local/bin/"
    install -Dm755  "rollback-home" -t "$pkgdir/usr/local/bin/"
    install -Dm755  "restoefi" -t "$pkgdir/usr/local/bin/"
    install -Dm755  "btrfsassistant-rb" -t "$pkgdir/usr/local/bin/"

    }
