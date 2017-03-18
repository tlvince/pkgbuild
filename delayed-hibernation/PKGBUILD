# Maintainer: Chrysostomus @forum.manjaro.org
pkgname=delayed-hibernation
pkgver=0.1
pkgrel=3
pkgdesc="systemd hook to hibernate suspended system after a delay"
arch=(any)
url="https://github.com/Chrysostomus/$pkgname"
license=("MIT")
depends=('systemd')
makedepends=('git')
source=("git://github.com/Chrysostomus/$pkgname")
md5sums=('SKIP')

prepare () {
  cp /usr/lib/systemd/system/suspend.target "$srcdir"
  echo "Requires=suspend-to-hibernate.service" >> "$srcdir/suspend.target"
}

package () {
  cd "$srcdir"
  install -Dm644 "$srcdir/suspend.target" "$pkgdir/etc/systemd/system/suspend.target"
  install -Dm644 "$srcdir/$pkgname/suspend-to-hibernate.service" "$pkgdir/etc/systemd/system/suspend-to-hibernate.service"
}
