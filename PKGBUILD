# Contributor Calliope System <calliopesystem@gmail.com>

pkgname=lib32-com.paragon.mounter
pkgver=1.0.0
_pkgver=2.0.4
pkgrel=1
pkgdesc="Paragon UFSD Root Mounter utilities. Contains file system creation and checking utilities for HFS+ and NTFS."
arch=('x86_64')
license=('Proprietary')
url="https://web.archive.org/web/20230509055712/https://www.paragon-software.com/home/ufsd-root-mounter-android/"
# Statically linked x86 binaries
#depends=()
provides=("chkufsd=${_pkgver}" "mkhfs=${_pkgver}" "mkntfs=${_pkgver}" "mount_ufsd_fuse=${_pkgver}" "probe=${_pkgver}" "probe_2=${_pkgver}" "removedm=${_pkgver}" "removedm_2=${_pkgver}" "unmount=${_pkgver}" "unmount_2=${_pkgver}")
optdepends=('hfsutils: for HFS read and write support'
            'ntfs-3g: for legacy NTFS read write support and create resize support')
source=("https://archive.org/download/tools_202401/tools.zip")
sha512sums=('2ea8861cc7b4169d34f29a6283f63f6f0131b8216cc5c53331fc3e451d534ae0fd2f18251d2e1666c5ed97d9689be3abeaa55c4b0cc9559a9147818422ed02dd')

package() {
  cd "${srcdir}/disk tools"
  mkdir "${pkgdir}/usr"
  mkdir "${pkgdir}/usr/bin"
  install -m755 chkufsd "${pkgdir}/usr/bin/chkufsd"
  install -m755 mkhfs "${pkgdir}/usr/bin/mkhfs"
  #install -m755 mkntfs "${pkgdir}/usr/bin/mkntfs" #PROVIDED BY NTFS-3G
  install -m755 mount_ufsd_fuse "${pkgdir}/usr/bin/mount_ufsd_fuse"
  install -m755 probe "${pkgdir}/usr/bin/probe"
  install -m755 probe_2 "${pkgdir}/usr/bin/probe_2"
  install -m755 removedm "${pkgdir}/usr/bin/removedm"
  install -m755 removedm_2 "${pkgdir}/usr/bin/removedm_2"
  install -m755 unmount "${pkgdir}/usr/bin/unmount"
  install -m755 unmount_2 "${pkgdir}/usr/bin/unmount_2"
  ln -s /usr/bin/chkufsd "${pkgdir}/usr/bin/chkntfs"
  ln -s /usr/bin/chkufsd "${pkgdir}/usr/bin/chkhfs"
}
