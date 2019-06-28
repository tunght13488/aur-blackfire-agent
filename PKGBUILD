# Maintainer: Jérôme Deuchnord <jerome@deuchnord.fr>
# Contributor: Morris Jobke <hey AT morrisjobke DOT de>
# Contributor: Massimiliano Torromeo <massimiliano.torromeo@gmail.com>

pkgname=blackfire-agent
pkgver=1.26.1
pkgrel=1
pkgdesc='Blackfire Profiler Agent - Fire up your PHP Apps Performance'
arch=('i686' 'x86_64')
url='https://blackfire.io'
license=('custom')
install='blackfire-agent.install'
depends=('glibc')

source=('blackfire-agent.service')
source_i686=("blackfire-agent-${pkgver}_i686::http://packages.blackfire.io/binaries/blackfire-agent/$pkgver/blackfire-agent-linux_386")
source_x86_64=("blackfire-agent-${pkgver}_x86_64::http://packages.blackfire.io/binaries/blackfire-agent/$pkgver/blackfire-agent-linux_amd64")

sha256sums=('aec343bca2f712d0dd22ccb43128d479e0280847e9573c2f37c183478f1ebcf6')
sha256sums_i686=('5ff9531bd6ad7bba82af3322ae7dde743be715351df00a32ca59314d7712e319')
sha256sums_x86_64=('2e645a518075632c8321949a02b212675571c5249047783e3cece2ccad5ab93e')

package(){
  install -dm 755 "$pkgdir"/etc/blackfire
  chown 487:487 "$pkgdir"/etc/blackfire
  install -dm 755 "$pkgdir"/var/log/blackfire

  install -Dm 755 blackfire-agent.service "$pkgdir"/usr/lib/systemd/system/blackfire-agent.service
  install -Dm 755 blackfire-agent-${pkgver}_$CARCH "$pkgdir"/usr/bin/blackfire-agent
}
