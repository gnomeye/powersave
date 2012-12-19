# Maintainer: Simon Gomizelj <simongmzlj@gmail.com>

pkgname=powersave
pkgver=20121219
pkgrel=1
pkgdesc="powersaving script"
arch=('any')
url="http://github.com/gnomeye/powersave"
license=('GPL')
depends=('systemd' 'backlight-utils-git')
makedepends=('git')

_gitroot="$PWD"
_gitname="powersave"

build() {
  msg "Connecting to GIT server...."

  if [[ -d $_gitname ]] ; then
    cd "$_gitname" && git pull origin
    msg "The local files are updated."
  else
    git clone "$_gitroot" "$_gitname"
  fi

  msg "GIT checkout done or server timeout"
  msg "Starting make..."

  rm -rf "$srcdir/$_gitname-build"
  cp -r "$srcdir/$_gitname" "$srcdir/$_gitname-build"
  cd "$srcdir/$_gitname-build"
}

package() {
  cd "$srcdir/$_gitname-build"
  install -Dm644 50-powersave.rules "$pkgdir/etc/udev/rules.d/50-powersave.rules"
  install -Dm755 powersave "$pkgdir/usr/bin/powersave"
}

# vim: ft=sh syn=sh et
