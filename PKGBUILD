# Maintainer: Gabby <28601 dash gabby at users dot noreply dot gitlab dot freedesktop dot org>
# Maintainer: Julien <aur dot arch at fastmail dot com>
pkgname=snapper-rollback
pkgver=1.0.0
pkgrel=2
pkgdesc='Script to rollback snapper snapshots as described here https://wiki.archlinux.org/index.php/Snapper#Suggested_filesystem_layout'
arch=('any')
license=('GPL3')
url='https://github.com/jrabinow/snapper-rollback'
depends=('coreutils' 'python' 'btrfs-progs')
makedepends=('git')
provides=('snapper-rollback')
conflicts=('rollback-git' 'snapper-rollback')
replaces=('rollback-git')
backup=(etc/snapper-rollback.conf)
install=snapper-rollback.install
source=("git+https://github.com/jrabinow/snapper-rollback"
        "bootrestore.patch"
        "95_boot-backup.hook")
sha256sums=('SKIP'
            'SKIP'
            'f03bc257ef5b3bb38c94e654f87fe3d7656e02616989deb868ad02319923765f')


  prepare() {
cd "${srcdir}/${pkgname}"
# https://github.com/jrabinow/snapper-rollback/pull/6/commits
git cherry-pick -n 270cb8d3dd67d4d3cf895a52dc1714df8f8074c0
git cherry-pick -n 1ef412d8780e85674275a7bebc93e75ff7bde1ec
git cherry-pick -n fd6b05acd93dc68a61a4328e0ddf86d6d7f7738b
# patch -Np1  < ../bootrestore.patch
}

  package() {
    install -Dm 0644  "95_boot-backup.hook" -t "$pkgdir/usr/share/libalpm/hooks"
    install -Dm 0644  "$pkgname/snapper-rollback.conf" -t "$pkgdir/etc/"
    install -Dm 0755  "$pkgname/snapper-rollback.py" "$pkgdir/usr/bin/snapper-rollback"
}
