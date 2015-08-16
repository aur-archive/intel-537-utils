# Maintainer : Tobias Powalowski <tpowa@archlinux.org>

pkgname=intel-537-utils
pkgver=2.60.80.0
pkgrel=29
pkgdesc="Userspace tools for Intel Modem Drivers for 537 chipsets."
arch=(i686)
license=('custom:"INTEL537"')
url="http://linmodems.technion.ac.il/packages/Intel/"
depends=('bash' 'udev')
source=(http://linmodems.technion.ac.il/packages/intel/Philippe.Vouters/intel-5337EP_secure-2.60.80.0_2009_02_08.tar.bz2
        intel-537.rc.d)

build() {
  cd $startdir/src/intel-537EP_secure-2.60.80.0
  # Install driver loader
  install -D -m 755 hamregistry $pkgdir/usr/sbin/hamregistry
  # Install daemon
  install -D -m 755 $startdir/src/intel-537.rc.d $pkgdir/etc/rc.d/intel-537
  # install modem udev rule
  mkdir -p $pkgdir/etc/udev/rules.d
  echo 'KERNEL=="537[a-z][a-z,0-9]", MODE="0660", GROUP="tty", SYMLINK+="modem", RUN+="/lib/udev/load-modules.sh ppp-generic"' > $startdir/pkg/etc/udev/rules.d/intel537.rules
}
md5sums=('b5d2a258cddd28ede811bfaac41cec9b'
         '2ecaa11c40bd602941b39f61468eec2b')
