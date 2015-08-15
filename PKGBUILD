pkgname=craftbukkit-plugin-skylandsplus
pkgver=0.16b41
pkgrel=1
pkgdesc="Skylands world generator plugin for Bukkit"
arch=(any)
url="http://dev.bukkit.org/server-mods/skylandsplus"
license=("GPLv3")
makedepends=(dos2unix)
depends=("craftbukkit>=1.7.10")
optdepends=(craftbukkit-plugin-multiverse-core)
source=("http://bukkit.jacekk.co.uk:8000/job/SkylandsPlus/lastStableBuild/artifact/target/SkylandsPlus.jar")
md5sums=('SKIP')

pkgver() {
	find "$srcdir" -type f -exec dos2unix {} \;
	_vermajor=`cat "$srcdir"/plugin.yml | grep "version:\s" | awk '{ sub(/[^.0-9]+/, ""); print}'`
	_build=`cat "$srcdir"/META-INF/MANIFEST.MF | grep "Build-Number:\s" | awk '{print $2}'`
	echo ${_vermajor%-*}"b"${_build}
}

package() {
  install -Dm644 "$srcdir/SkylandsPlus.jar" "$pkgdir/srv/craftbukkit/plugins/SkylandsPlus.jar"
}

# vim:set ts=2 sw=2 et:
