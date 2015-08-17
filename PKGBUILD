# Maintainer: Jarek Sedlacek <jareksedlacek@gmail.com>

pkgname=vim-neocomplcache
pkgver=8.0
_scriptid=17867
pkgrel=2
pkgdesc="Ultimate auto completion system for Vim"
arch=('i686' 'x86_64')
url="http://www.vim.org/scripts/script.php?script_id=2620"
license=('custom')
groups=('vim-plugins')
install=vimdoc.install

source=(https://github.com/Shougo/neocomplcache/zipball/ver.$pkgver
        license.txt)

package() {
    install -d ${pkgdir}/usr/share/vim/vimfiles/{autoload,doc,indent,plugin,syntax}
    for x in doc; do
		install -Dm644 ${srcdir}/Shougo*/$x/* \
		${pkgdir}/usr/share/vim/vimfiles/$x/ || return 1;
	done
    cp -r ${srcdir}/Shougo*/autoload/* ${pkgdir}/usr/share/vim/vimfiles/autoload/ || return 1

    for x in plugin ; do
		install -Dm755 ${srcdir}/Shougo*/$x/neocomplcache.vim \
		${pkgdir}/usr/share/vim/vimfiles/$x/ || return 1;
        rm ${srcdir}/Shoug*/$x/neocomplcache.vim
		install -Dm755 -d ${srcdir}/Shougo*/$x/* \
		${pkgdir}/usr/share/vim/vimfiles/$x/ || return 1;
	done

    install -Dm644 ${srcdir}/license.txt ${pkgdir}/usr/share/licenses/${pkgname}/license.txt || return 1
}

md5sums=('bcad8a094bcdb4574fe5e07a83bfdee3'
         'efbd5986e691ce8c876fb86e8f5961ea')
