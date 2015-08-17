pkgname=starrypy
pkgver=1.2.3
pkgrel=2
pkgdesc="Plugin-driven Starbound proxy server built using Twisted."
arch=(any)
url="https://github.com/CarrotsAreMediocre/StarryPy"
license=("WTFPL")
install=starrypy.install
depends=(python2-twisted python2-sqlalchemy python2-enum34 python2-construct)
makedepends=(python2)
optdepends=("python2-nose: testsuite")
backup=("srv/starrypy/config/config.json.default")
source=("https://github.com/CarrotsAreMediocre/StarryPy/archive/v$pkgver.tar.gz"
"starrypy.sh")
md5sums=('fbbc196b6177fda290f8f0478b8b984b'
         '681dabb1214c046fd6f2db802eaf6a79')

package() {
	cd "${srcdir}"
	install -Dm755 "$srcdir/starrypy.sh" "$pkgdir/usr/bin/starrypy"
	cd StarryPy-$pkgver
	install -Dm644 LICENSE "$pkgdir/usr/share/licenses/starrypy/LICENSE"
	find . -name '*.json' -exec install -Dm644 {} "$pkgdir/srv/starrypy/"{} \;
	find . -name '*.py' -exec install -Dm644 {} "$pkgdir/srv/starrypy/"{} \;
	install -Dm644 config/config.json.default "$pkgdir/srv/starrypy/config/config.json.default"
	python2 -m compileall "$pkgdir"
} 
