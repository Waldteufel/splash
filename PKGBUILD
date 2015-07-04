# Maintainer: Benjamin Richter <br@waldteufel.eu>

pkgname=splash
pkgver=0.1
pkgrel=1
pkgdesc='Boot splash scripts'
arch=('i686' 'x86_64')
license=('custom:ISC')
url='http://www.archlinux.org'
optdepends=('fbv: to fill the framebuffer and dump it using mksplash')
source=('COPYING' 'splash' 'mksplash' 'splash.service' 'sd-splash.hook-install')
md5sums=('741d1fd57493ada92df663d0cf150817'
         '8012470baef48dd2b7dea5b789765175'
         'f85f85e9f8bcda664f0918674385149d'
         '0a2a17b9116578b3094839e420f9b058'
         '5d6c3b08e0c2c9f14302f46a0ac26c62')

package() {
  cd ${pkgdir}

  install -Dm755 ${srcdir}/mksplash usr/bin/mksplash
  install -Dm755 ${srcdir}/splash usr/lib/splash/splash

  install -Dm644 ${srcdir}/sd-splash.hook-install usr/lib/initcpio/install/sd-splash
  install -Dm644 ${srcdir}/splash.service usr/lib/systemd/system/splash.service

  install -d usr/lib/systemd/system/initrd.target.wants/
  ln -s ../splash.service usr/lib/systemd/system/initrd.target.wants/splash.service

  install -Dm644 ${srcdir}/COPYING usr/share/licenses/${pkgname}/COPYING
}

# vim:set ts=2 sw=2 et:
