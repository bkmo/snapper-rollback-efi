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
source=("git+https://github.com/bkmo/snapper-rollback-efi"
        "04-snap-efi-pre-backup.hook"
        "zz-snap-efi-post-backup.hook"
        "rollback")
sha256sums=('SKIP'
            '896092a3feaa997ce510916a446b2721def69a451ab378ec5fd5df9f1e4b8c1b'
            '1c1143cd433d9323d13baab7dbcd76ee8c8d1249c70fa6eee69a8d316b9885cf'
            '748676045d28fd9bcd35601754826e50cf60c70b075c1d29bb545e555347e948' )


    package() {
    install -Dm 0644  "zz-snap-efi-post-backup.hook" -t "$pkgdir/usr/share/libalpm/hooks/"
    install -Dm 0644  "04-snap-efi-pre-backup.hook" -t "$pkgdir/usr/share/libalpm/hooks/"
    install -Dm 0644  "$pkgname/snapper-rollback.conf" -t "$pkgdir/etc/"
    install -Dm 0755  "$pkgname/snapper-rollback" -t "$pkgdir/usr/bin/"
    install -Dm 0755  "rollback" -t "$pkgdir/usr/bin/
}
