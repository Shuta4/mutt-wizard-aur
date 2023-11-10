# Maintainer: Shuta4 <shuta4@proton.me>

_pkgname=mutt-wizard
pkgname="s4-$_pkgname"
pkgver=3.2.1
pkgrel=1
pkgdesc="Easily auto-configure neomutt and isync/mpop with safe passwords (IMAP/POP3/SMTP) custom build"
url="https://github.com/Shuta4/mutt-wizard"
arch=('any')
license=('GPL3')
options=(zipman)
depends=('neomutt' 'isync' 'msmtp' 'notmuch-runtime' 'pass' 'curl' 'libnotify' 'perl')
optdepends=('imagemagick: view images inside of the neomutt TUI'
            'w3m: view HTML email and images inside of the neomutt TUI'
            'lynx: view HTML email inside of the neomutt TUI'
            'links: view HTML email inside of the neomutt TUI'
            'elinks: view HTML email inside of the neomutt TUI'
            'urlview: list URLs found in mails to open them in a browser'
            'abook: contact store and tab completion'
            'protonmail-bridge: use neomutt with protonmail accounts'
            'pam-gnupg: automatically unlock gpg keys at session login'
            'cron: set up automatic mail syncing'
            'mpop: if you want to use POP3 email access')
source=("https://github.com/Shuta4/$_pkgname/archive/refs/tags/v$pkgver-$pkgrel.tar.gz")
sha256sums=('d1c5461ee950350560e368b99c65c3227f00f2c3e8f28804b9314b8dc3674b5f')
install="$_pkgname.install"

provides=("${_pkgname}")
conflicts=("${_pkgname}")

package() {
  cd "$srcdir/$_pkgname-$pkgver-$pkgrel"
  make PREFIX=/usr DESTDIR="$pkgdir" -s install
  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$_pkgname/LICENSE"
  install -Dm644 README.md "$pkgdir/usr/share/doc/$_pkgname/README.md"
}
