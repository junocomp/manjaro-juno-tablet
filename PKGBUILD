# Maintainer: Giovanni Caligaris <uk@junocomputers.com>
pkgname=juno-tablet
pkgver=0.1.2
pkgrel=2
pkgdesc="Manjaro Drivers for Juno Tablet"
arch=(any)
license=('GPL3')
depends=('flatpak' 'plocate' 'firefox' 'sof-firmware' 'thermald' 'irqbalance' 'curl' 'sof-firmware' 'mobile-config-firefox' 'powertop' 'iio-sensor-proxy' 'python-gobject' 'power-profiles-daemon' 'acpi' 'gst-plugin-pipewire' 'gst-plugin-libcamera' 'pipewire-v4l2' 'iw')
install=${pkgname}.install
source=('10_juno-debian-settings.gschema.override'
		'61-sensor-local.hwdb'
		'70-wifi-pm.rules'
		'alsa-ucm-conf.hook'
		'external-display-power-profile.rules'
		'HiFi.conf'
		'juno.pa'
		'juno-login.conf'
		'juno-monitor'
		'juno-pp'
		'juno-pp.service'
		'juno-profile.sh'
		'juno-sleep.conf'
		'juno-suspend'
		'juno-turbo.rules'
		'override.conf'
		'power-profiles.rules'
		'powertop.rules'
		'powertop.service'
		'powertop-usb-mouse'
		'replace-hifi'
		'restore-alsa'
		'resume'
		'squeekboard.rules'
		'systemd.hook'
		'terminal-clean'
		'turbo-off'
		'turbo-on'
		'turbo-stat')
sha256sums=('d38e48eebc50662026bb702bf222b1586550412c091ed00b40db4e1e7f61ee16'
            'a75af204066528231c7b5092709cb1dbc264a0a7c0dbf1d2749c19e038f2f585'
            'bba0fbd87f85dc19bd7d01baeaff4ce94d97111678ed5ab69f02239db35759ec'
            '3b9654a7e046bf31be904c39bd15306236b0fc55b5479077791feab82562bce4'
            '20573e3e96b879a1f8526b93c4ed469ee1fadcd9d8518396105de18c4abb6a2b'
            '76482b710b439a5eea5efab08b00c71312841dca4ea1c7b51abdc67d78fbc1e9'
            '770f93f4463aca16a947d2a7e01d79dce13f57c6c4375edf82d38138b9eebcb0'
            '26a3583899ed857e1c5572d1c1c01b8300196bad40bc84b689f7476a8e76739e'
            'fe01b53f63f631d6096f6f9e9177514484317d9293896955644dd2c8591fe552'
            '9f89ce586a6161cdc017ac7857fe42946607cf260c417974af2b753b8fbedbe0'
            '85f3284fcef70cb511bfb691aeea5cc6bf3478fb67ac9c4f86eb4437e56f8ac2'
            '3bc30e02be5e86bad1284e9e61a77b99525cd38a0e3bfb6ea9323bdbf4a7eeb3'
            'a65bac6b0dd3d696eaf063a3f1e2509d36c6019a39bc09d8e0f67515d839fdeb'
            '70d26bf610568cfe749ed0db2e49911add471d2c084c41df589f376eae561572'
            '9e0f385ca3575c8db9cc7bc1683a06ce95975cbc5453e3c0c2667c24acb48d1e'
            '113378f8b416f01d4e6ef351ae900fa69ef11f3cb47032e0e6ad8e9b2b7df6ab'
            '70c25a74d3dcff6d0d1d021a456b706e94a88c89400883d1a4e345147f6e1358'
            'c85a38d5b08b11edb819737594e853dc17a52b05283b0bbafaab8c9a070e1ff3'
            '683dd7ef7d984c2978585980c99715bbb2f01395d9279bf9f4bcef5444b97a1f'
            '08938d3359c2da6930c147d02f6bd5466e5d96d78bb3e0426604912662692262'
            '241cd42ee1811f265e56f32a30cc404b573e4dff9fc812f9a0aceaa07eed1ff1'
            '05cd3f8c53e185e081d51b606ae20084f59e2555f8b5325a29f2ae513201ff52'
            'c656ec750e48b0675876d3d59de601ac92a894f86ad7183da2601f58dd5095ca'
            'c5bdce86ecb3c4a7824af030093b9cf5d2380868b17612a5b20b5a6fe5b2897c'
            '48e7176104bfda66d5a043eedc5a1575774ce66fcc62480ee1834c35b27b6eb7'
            'bb5b44b2ce1467e0b056f6935d097c11c76329b4db6e7caf7f23c49609c0d042'
            '89aacd3c507902871cf2e14e1a4fcdfa0c564f8e7dae9cfd5f361606af3e3ce6'
            'a49965b5426db2ef5ab2d6ee2af6374d45e37c44284cbae5f6617e2becbc421e'
            'a812a8ceb4518e879d642a810bceea7b46c12704d1e0ab9bc2c6e7fe388a78a6')
package () {
  # Create folders
  mkdir -p $pkgdir/etc/udev/rules.d/
  mkdir -p $pkgdir/etc/udev/hwdb.d/
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
  cp 70-wifi-pm.rules $pkgdir/etc/udev/rules.d/
  cp power-profiles.rules $pkgdir/etc/udev/rules.d/
  cp powertop.rules $pkgdir/etc/udev/rules.d/
  cp external-display-power-profile.rules $pkgdir/etc/udev/rules.d/
  cp squeekboard.rules $pkgdir/etc/udev/rules.d/
  cp juno-turbo.rules $pkgdir/etc/udev/rules.d/
  cp 61-sensor-local.hwdb $pkgdir/etc/udev/hwdb.d/
    
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
