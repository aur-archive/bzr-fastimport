# Maintainer:  Martin Wimpress <code@flexion.org>
# Contributor: Martin Panter <vadmium+aur@gmail.com>
# Contributor: Hector Acosta <hector.acosta@gmail.com>
# Contributor: Kambus
# Contributor: Mario Danic <mario.danic>

pkgname=bzr-fastimport
pkgver=0.13.0
pkgrel=3
pkgdesc="Bazaar Fast Import is a plugin providing fast loading of revision control data into Bazaar."
arch=(i686 x86_64)
url="https://launchpad.net/${pkgname}"
license=('GPL2')
groups=(bzr)
depends=('python2' 'bzr' 'python2-fastimport')
makedepends=('bzr')
conflicts=(bzr-fastimport-russo79-bzr bzr-fastimport-deleted-entries-fix)
source=(http://launchpad.net/${pkgname}/trunk/${pkgver}/+download/${pkgname}-${pkgver}.tar.gz)
md5sums=('e47115774d44ae0c3b027ae0374aa52e')

prepare() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    for _file in $(grep '#!/usr/bin/.*python' -r . | cut -d: -f1); do
        sed -i 's/python/python2/' "$_file"
    done
}

package() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    python2 setup.py install --prefix'=/usr' --root="${pkgdir}"
}
