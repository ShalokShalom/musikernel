pkgname=musikernel2
pkgver=16.02.1
pkgrel=1
pkgdesc="DAW and suite of instrument & effect plugins"
arch=('x86_64')
url="https://github.com/j3ffhubb/musikernel"
license=('GPL3')
depends=('ffmpeg' 'lame' 'libisofs' 'liblo' 'portaudio-svn' 'portmidi'
         'python3-numpy' 'pyqt5-python3'
         'rubberband' 'sbsms' 'squashfs-tools' 'vorbis-tools')
makedepends=('gdb' 'git')
source=(https://github.com/j3ffhubb/musikernel/archive/${pkgname}-${pkgver}.tar.gz)
sha256sums=(SKIP)

build(){
  cd ${pkgname}/src
  make PREFIX="/usr"
}

package() {
  cd ${pkgname}/src
  make DESTDIR=${pkgdir} install
  # remove setuid/setgid
  chmod 755 ${pkgdir}/usr/bin/musikernel2-engine
}
