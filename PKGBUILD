pkgname=franz
pkgver=5.0.0_beta.18
dlver=5.0.0-beta.18
pkgrel=1
pkgdesc="A free messaging app for WhatsApp, Facebook Messenger, Telegram, Slack and more."
arch=('x86_64')
url="http://meetfranz.com/"
license=("custom")
depends=('alsa-lib' 'gconf' 'gtk3' 'libnotify' 'libxtst' 'nss' 'python2' 'libxkbfile')
source=("$pkgname.desktop" "$pkgname.png" "https://github.com/meetfranz/franz/releases/download/v$dlver/franz-$dlver.tar.gz")
sha256sums=('fce6efcaf265492eb9bf479795e49b2868114c157709acc849302a9520919ab2'
            '6e761371afadf155b8bc25e94fd7de371c16130a87338300e5800924916a7a28'
            '96090ae3722f43c2f03ea9412edaf1436a25fc19bbccf30ab1f0fe494ec01825')
            
package() {
	install -dm755 "$pkgdir/opt/$pkgname"
	cp -r $srcdir/$pkgname-$dlver/* $pkgdir/opt/$pkgname/
	install -dm755 "$pkgdir/usr/bin"
	echo -en "#!/bin/bash\nexec /opt/$pkgname/franz $@"  >"$pkgdir/usr/bin/franz"
    chmod +x  "$pkgdir/usr/bin/franz"
	install -dm755 "$pkgdir/usr/share/pixmaps"
	install -Dm644 "$srcdir/$pkgname.png" "$pkgdir/usr/share/icons/hicolor/256x256/apps/$pkgname.png"
	install -dm755 "$pkgdir/usr/share/applications"
	install -Dm644 "$srcdir/$pkgname.desktop" "$pkgdir/usr/share/applications/$pkgname.desktop"
}
