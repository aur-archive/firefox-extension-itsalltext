# Maintainer: Vain <aurmaint1 on host: uninformativ dot de>

_plugin_name=itsalltext
_plugin_version=1.9.1.1
_plugin_id=4125
pkgdesc="Edit textareas in your favorite editor"
license=('GPL3')

pkgname=firefox-extension-$_plugin_name
pkgver=$_plugin_version
pkgrel=1
arch=('any')
url="https://addons.mozilla.org/firefox/addon/$_plugin_id"
depends=('firefox')
source=("https://addons.mozilla.org/firefox/downloads/latest/$_plugin_id/addon-$_plugin_id-latest.xpi")
md5sums=('98049342056258911629f5ebe60f168b')

package() {
  cd "$srcdir"
  emid=$(sed -n '/.*<em:id>\(.*\)<\/em:id>.*/{s//\1/p;q}' install.rdf)
  dstdir=$pkgdir/usr/lib/firefox/browser/extensions/$emid
  install -d "$dstdir"
  mv * "$dstdir"
  rm "$dstdir"/*.xpi
}
