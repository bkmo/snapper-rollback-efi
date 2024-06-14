# Maintainer: Gabby <28601 dash gabby at users dot noreply dot gitlab dot freedesktop dot org>
# Maintainer: Julien <aur dot arch at fastmail dot com>
pkgname=snapper-rollback-efi
pkgver=1.0.0
pkgrel=1
pkgdesc='Script to rollback snapper snapshots as described here https://wiki.archlinux.org/index.php/Snapper#Suggested_filesystem_layout'
arch=('any')
license=('GPL3')
url='https://github.com/jrabinow/snapper-rollback'
depends=('coreutils' 'python' 'btrfs-progs')
makedepends=('git')
provides=('snapper-rollback')
conflicts=('rollback-git' 'snapper-rollback')
replaces=('rollback-git' 'snapper-rollback')
backup=(etc/snapper-rollback.conf)
install=snapper-rollback.install
source=("git+https://github.com/bkmo/snapper-rollback-boot"
        "95_boot-backup.hook")
sha256sums=('SKIP'
            'aceeb7bcac926da551b1f7f1a32df818377cd21cfec76c851c11836ac6c2dc3d')


    package() {
    install -Dm 0644  "95_boot-backup.hook" "$pkgdir/usr/share/libalpm/hooks/zz-snap-efi-backup.hook"
    install -Dm 0644  "$pkgname/snapper-rollback.conf" -t "$pkgdir/etc/"
    install -Dm 0755  "$pkgname/snapper-rollback.py" "$pkgdir/usr/bin/snapper-rollback"
}
