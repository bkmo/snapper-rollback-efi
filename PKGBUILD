# Maintainer: Gabby <28601 dash gabby at users dot noreply dot gitlab dot freedesktop dot org>
# Maintainer: Julien <aur dot arch at fastmail dot com>
pkgname=snapper-rollback-efi
pkgver=1.0.1
pkgrel=1
pkgdesc='Script to rollback snapper snapshots as described here https://wiki.archlinux.org/index.php/Snapper#Suggested_filesystem_layout'
arch=('any')
license=('GPL3')
url='https://github.com/bkmo/snapper-rollback-efi'
depends=('coreutils' 'python' 'btrfs-progs' 'snapper')
makedepends=('git')
provides=('snapper-rollback')
conflicts=('rollback-git' 'snapper-rollback''snapper-rollback-boot')
replaces=('rollback-git' 'snapper-rollback''snapper-rollback-boot')
backup=(etc/snapper-rollback.conf)
source=("$url/archive/refs/tags/$pkgver.tar.gz")
sha256sums=('SKIP')

    package() {
    cd $pkgname-$pkgver
    install -Dm 0644  "04-snap-efi-backup.hook" "$pkgdir/usr/share/libalpm/hooks/zzz-efi-backup.hook"
    install -Dm644  "snapper-rollback.conf" -t "$pkgdir/etc/"
    install -Dm755  "snapper-rollback.py" "$pkgdir/usr/bin/snapper-rollback"
    install -Dm 0755  "rollback" -t "$pkgdir/usr/bin/"
    }
