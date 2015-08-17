# Generator  : CPANPLUS::Dist::Arch 1.19

pkgname='perl-unicode-collate-biber'
_perlname='Unicode-Collate'
pkgver='1.07'
pkgrel='1'
pkgdesc="Unicode Collation Algorithm"
arch=('any')
license=('PerlArtistic' 'GPL')
options=('!emptydirs')
depends=('perl')
makedepends=()
provides=(perl-unicode-collate=1.07)
url='http://search.cpan.org/dist/Unicode-Collate'
source=("http://search.cpan.org/CPAN/authors/id/S/SA/SADAHIRO/${_perlname}-${pkgver}.tar.gz")

build() {
  ( export PERL_MM_USE_DEFAULT=1 PERL5LIB=""                 \
      PERL_AUTOINSTALL=--skipdeps                            \
      PERL_MM_OPT="INSTALLDIRS=site DESTDIR='$pkgdir' \
      INSTALLSITEMAN1DIR='/usr/local/share/man/man1' INSTALLSITEMAN3DIR='/usr/local/share/man/man3' " \
      PERL_MB_OPT="--installdirs site --destdir '$pkgdir'" \
      MODULEBUILDRC=/dev/null

    cd "${srcdir}/${_perlname}-${pkgver}"
    /usr/bin/perl Makefile.PL
    make
  )
}

check() {
  cd "${srcdir}/${_perlname}-${pkgver}"
  ( export PERL_MM_USE_DEFAULT=1 PERL5LIB=""
    make test
  )
}

package() {
  cd "${srcdir}/${_perlname}-${pkgver}"
  make install
  find "$pkgdir" -name .packlist -o -name perllocal.pod -delete
}

md5sums=('80b9d8452be51a638268fffd129d2480')
