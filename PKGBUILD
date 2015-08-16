# Contributor: Massimiliano Torromeo <massimiliano.torromeo@gmail.com>
# Contributor: Parth Buch <parthbuch115 at gmail dot com>
# Contributor: Tom Vincent <http://tlvince.com/contact/>
# Contributor: Valentin Haloiu <vially.ichb+aur@gmail.com>
# Contributor: Cluxter <contact@cluxter.email>
# Maintainer: Arthur Zamarin <arthurzam@gmail.com>

pkgname=meteorjs
pkgver=1.1.0.2
pkgrel=2
pkgdesc="Open-source platform for building top-quality web apps in a fraction of the time."
arch=('i686' 'x86_64')
url="https://github.com/meteor/meteor"
license=('MIT')
depends=('nodejs' 'mongodb')
options=('!strip')

source_i686=("https://d3sqy0vbqsdhku.cloudfront.net/packages-bootstrap/$pkgver/meteor-bootstrap-os.linux.x86_32.tar.gz")
source_x86_64=("https://d3sqy0vbqsdhku.cloudfront.net/packages-bootstrap/$pkgver/meteor-bootstrap-os.linux.x86_64.tar.gz")

sha256sums_i686=('3fdddd00f380468c6ddc1ab151c09942e928054837a0a727eae68b15d6f606b9')
sha256sums_x86_64=('9dcc4ba6698eaa09016ff8cb8b77704fe31916e8ac86b54796f7e5e591cecaf6')

package() {
    mkdir -p "$pkgdir/opt"
    mv .meteor "$pkgdir/opt/meteor"
    mkdir -p "$pkgdir/usr/bin/"
    METEOR_SYMLINK_TARGET="$(readlink "$pkgdir/opt/meteor/meteor")"
    METEOR_TOOL_DIRECTORY="$(dirname "$METEOR_SYMLINK_TARGET")"

    LAUNCHER="$pkgdir/opt/meteor/$METEOR_TOOL_DIRECTORY/scripts/admin/launch-meteor"
    cp "$LAUNCHER" "$pkgdir/usr/bin/meteor"
}
