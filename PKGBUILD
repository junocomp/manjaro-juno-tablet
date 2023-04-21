# Maintainer: Giovanni Caligaris <uk@junocomputers.com>
pkgname=juno-tablet
pkgver=0.1.0
pkgrel=9
pkgdesc="Manjaro Drivers for Juno Tablet"
arch=(any)
license=('GPL3')
depends=('flatpak' 'plocate' 'firefox' 'sof-firmware' 'thermald' 'irqbalance' 'curl' 'sof-firmware' 'mobile-config-firefox' 'powertop' 'iio-sensor-proxy' 'python-gobject' 'power-profiles-daemon' 'acpi')
install=${pkgname}.install
source=(10_juno-debian-settings.gschema.override
	61-sensor-local.hwdb
	70-wifi-pm.rules
	99-inverted-touchscreen.rules
	alsa-ucm-conf.hook
	external-display-power-profile.rules
	HiFi.conf
	juno.pa
	juno-login.conf
	juno-monitor
	juno-pp
	juno-pp.service
	juno-profile.sh
	juno-sleep.conf
	juno-suspend
	juno-turbo.rules
	override.conf
	power-profiles.rules
	powertop.rules
	powertop.service
	powertop-usb-mouse
	replace-hifi
	restore-alsa
	resume
	squeekboard.rules
	systemd.hook
	terminal-clean
	turbo-off
	turbo-on
	turbo-stat)
sha256sums=('SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP')
package () {
  # Create folders
  mkdir -p $pkgdir/etc/udev/hwdb.d/
  mkdir -p $pkgdir/etc/udev/rules.d/
  mkdir -p $pkgdir/etc/systemd/system/
  mkdir -p $pkgdir/etc/systemd/logind.conf.d
  mkdir -p $pkgdir/etc/systemd/sleep.conf.d
  mkdir -p $pkgdir/usr/share/juno
  mkdir -p $pkgdir/etc/pacman.d/hooks
  mkdir -p $pkgdir/etc/profile.d/
  mkdir -p $pkgdir/etc/pulse/default.pa.d/
  mkdir -p $pkgdir/usr/bin
  mkdir -p $pkgdir/usr/share/glib-2.0/schemas/
  mkdir -p $pkgdir/etc/systemd/system/powertop.service.d
  
  # Rules and HWDB
  cp 61-sensor-local.hwdb $pkgdir/etc/udev/hwdb.d/
  cp 70-wifi-pm.rules $pkgdir/etc/udev/rules.d/
  cp 99-inverted-touchscreen.rules $pkgdir/etc/udev/rules.d/
  cp power-profiles.rules $pkgdir/etc/udev/rules.d/
  cp powertop.rules $pkgdir/etc/udev/rules.d/
  cp external-display-power-profile.rules $pkgdir/etc/udev/rules.d/
  cp squeekboard.rules $pkgdir/etc/udev/rules.d/
  cp juno-turbo.rules $pkgdir/etc/udev/rules.d/
    
  #Systemd
  cp juno-login.conf $pkgdir/etc/systemd/logind.conf.d/
  cp juno-sleep.conf $pkgdir/etc/systemd/sleep.conf.d
  cp juno-suspend $pkgdir/usr/share/juno
  cp resume $pkgdir/usr/share/juno
  chmod a+x $pkgdir/usr/share/juno/juno-suspend
  chmod a+x $pkgdir/usr/share/juno/resume
  cp systemd.hook $pkgdir/etc/pacman.d/hooks
  cp powertop.service $pkgdir/etc/systemd/system/
  cp powertop-usb-mouse $pkgdir/usr/bin
  chmod a+x $pkgdir/usr/bin/powertop-usb-mouse
  cp juno-pp.service $pkgdir/etc/systemd/system/
  cp juno-pp $pkgdir/usr/bin
  chmod a+x $pkgdir/usr/bin/juno-pp
  cp override.conf $pkgdir/etc/systemd/system/powertop.service.d
  
  # SOF-Firmware
  cp HiFi.conf $pkgdir/usr/share/juno
  cp juno.pa $pkgdir/etc/pulse/default.pa.d/
  cp replace-hifi $pkgdir/usr/share/juno/
  chmod a+x $pkgdir/usr/share/juno/replace-hifi
  cp alsa-ucm-conf.hook $pkgdir/etc/pacman.d/hooks
  cp restore-alsa $pkgdir/usr/bin
  chmod a+x $pkgdir/usr/bin/restore-alsa
  
  # Mozilla Wayland settings
  cp juno-profile.sh $pkgdir/etc/profile.d/
  
  # Schemas
  cp 10_juno-debian-settings.gschema.override $pkgdir/usr/share/glib-2.0/schemas/
  
  # Turbo
  cp turbo-off $pkgdir/usr/bin
  cp turbo-on $pkgdir/usr/bin
  cp turbo-stat $pkgdir/usr/bin
  cp juno-monitor $pkgdir/usr/bin
  chmod a+x $pkgdir/usr/bin/turbo-off
  chmod a+x $pkgdir/usr/bin/turbo-on
  chmod a+x $pkgdir/usr/bin/turbo-stat
  chmod a+x $pkgdir/usr/bin/juno-monitor
  
  # Terminal Clean
  cp terminal-clean $pkgdir/usr/bin

  }
