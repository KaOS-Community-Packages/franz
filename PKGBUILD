pkgname=franz
pkgver=0.9.10
pkgrel=1
pkgdesc="A free messaging app for WhatsApp, Facebook Messenger, Telegram, Slack and more."
arch=( 'x86_64')
url="http://meetfranz.com/"
license=("custom")
depends=('gconf' 'gtk2' 'libxtst' 'nss' 'alsa-lib' 'libnotify' 'fontconfig')
source=("$pkgname.desktop" "$pkgname.png" "https://github.com/imprecision/franz-app/releases/download/$pkgver/Franz-linux-x64-$pkgver.tgz")
sha256sums=('fce6efcaf265492eb9bf479795e49b2868114c157709acc849302a9520919ab2'
            '6e761371afadf155b8bc25e94fd7de371c16130a87338300e5800924916a7a28'
            '54d98067a2c411a90046f80ba5c83517239caf1df83d3f9f8be4dbe82f2b5a6f')

package() {
	cd "$srcdir/"
	install -dm755 "$pkgdir/usr/bin"
	install -dm755 "$pkgdir/usr/share/$pkgname"
	cp -r $srcdir/* $pkgdir/usr/share/$pkgname/
	install -dm755 "$pkgdir/usr/bin"
	echo -en "#!/bin/bash\nexec /usr/share/$pkgname/Franz $@"  >"$pkgdir/usr/bin/franz"
    chmod +x  "$pkgdir/usr/bin/franz"
	install -dm755 "$pkgdir/usr/share/pixmaps"
	install -Dm644 "$srcdir/$pkgname.png" "$pkgdir/usr/share/pixmaps/franz.png"
	install -dm755 "$pkgdir/usr/share/applications"
	install -Dm644 "$srcdir/$pkgname.desktop" "$pkgdir/usr/share/applications/franz.desktop"

	rm -r $pkgdir/usr/share/$pkgname/{$pkgname.png,Franz-linux-x64-$pkgver.tgz,$pkgname.desktop}

}
