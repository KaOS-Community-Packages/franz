pkgname=franz
pkgver=5.0.1
pkgrel=1
pkgdesc="A free messaging app for WhatsApp, Facebook Messenger, Telegram, Slack and more."
arch=('x86_64')
url="http://meetfranz.com/"
license=("custom")
depends=('alsa-lib' 'gconf' 'gtk3' 'libnotify' 'libxtst' 'nss' 'python2' 'libxkbfile')
source=("$pkgname.desktop" "$pkgname.png" "https://github.com/meetfranz/${pkgname}/releases/download/v${pkgver}/${pkgname}-${pkgver}.tar.gz")
sha256sums=('fce6efcaf265492eb9bf479795e49b2868114c157709acc849302a9520919ab2'
            '6e761371afadf155b8bc25e94fd7de371c16130a87338300e5800924916a7a28'
            'e9b62eeaba80e4bbad22165f7c9db1a29a64f6e46c327188f61bee9974f5ec98')
package() {
	install -dm755 "$pkgdir/opt/$pkgname"
	cp -r $srcdir/$pkgname-$pkgver/* $pkgdir/opt/$pkgname/
	install -dm755 "$pkgdir/usr/bin"
	echo -en "#!/bin/bash\nexec /opt/$pkgname/franz $@"  >"$pkgdir/usr/bin/franz"
	chmod +x  "$pkgdir/usr/bin/franz"
	install -dm755 "$pkgdir/usr/share/pixmaps"
	install -Dm644 "$srcdir/$pkgname.png" "$pkgdir/usr/share/icons/hicolor/256x256/apps/$pkgname.png"
	install -dm755 "$pkgdir/usr/share/applications"
	install -Dm644 "$srcdir/$pkgname.desktop" "$pkgdir/usr/share/applications/$pkgname.desktop"
}
