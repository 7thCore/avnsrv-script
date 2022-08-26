#    Copyright (C) 2022 7thCore
#    This file is part of AvnSrv-Script.
#
#    AvnSrv-Script is free software: you can redistribute it and/or modify
#    it under the terms of the GNU General Public License as published by
#    the Free Software Foundation, either version 3 of the License, or
#    (at your option) any later version.
#
#    AvnSrv-Script is distributed in the hope that it will be useful,
#    but WITHOUT ANY WARRANTY; without even the implied warranty of
#    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
#    GNU General Public License for more details.
#
#    You should have received a copy of the GNU General Public License
#    along with this program.  If not, see <http://www.gnu.org/licenses/>.

pkgname=avnsrv-script
pkgver=1.2
pkgrel=2
pkgdesc='Avorion server script for running the server on linux.'
arch=('x86_64')
license=('GPL3')
depends=('bash'
         'coreutils'
         'sudo'
         'grep'
         'sed'
         'awk'
         'curl'
         'rsync'
         'wget'
         'findutils'
         'tmux'
         'jq'
         'zip'
         'unzip'
         'p7zip'
         'postfix'
         's-nail'
         'steamcmd')
install=avnsrv-script.install
source=('bash_profile'
        'avnsrv-mkdir-tmpfs@.service'
        'avnsrv-script.bash'
        'avnsrv-send-notification@.service'
        'avnsrv@.service'
        'avnsrv-timer-1.service'
        'avnsrv-timer-1.timer'
        'avnsrv-timer-2.service'
        'avnsrv-timer-2.timer'
        'avnsrv-tmpfs@.service')
sha256sums=('f1e2f643b81b27d16fe79e0563e39c597ce42621ae7c2433fd5b70f1eeab5d63'
            'fda540235eefe5766bb361f3baaf98bc838499dd3a090619c759635a1bc96f64'
            'ceb5d8fe8a82cfedaefb673316c18d6e64b729304afd626da240bada85e7da4c'
            'b372bba5101c13c04148724dc56f2686906bbeb919883d33c76b2101e8286ee2'
            '941ae96e2e35ea45f9a4dbe43e64073be1161f451273d88dbe6c0666b01944b9'
            '9de872b1fbaa9de17efad7c837b24f7a78099bd8a2a53cc2a01d733ff98ed5eb'
            'e125c9e09ded898d17a0cebc8364c18be197151933e6b8a9aa07c6a32cf15f46'
            '7cbf79572aa190bdb52017c4b2036f8bb98c281248c4b270fdec43df2cd80f69'
            'd1bac7525488894cfdaabb0965c77ecb27e5844ba8b2aed56ee40c7c072e368e'
            '3e0c777d5301186756ed8a2e64c754c9df492d2da8802f003bf5aff74ab68b04')

package() {
  install -d -m0755 "${pkgdir}/usr/bin"
  install -d -m0755 "${pkgdir}/srv/avnsrv"
  install -d -m0755 "${pkgdir}/srv/avnsrv/server"
  install -d -m0755 "${pkgdir}/srv/avnsrv/config"
  install -d -m0755 "${pkgdir}/srv/avnsrv/config/environments"
  install -d -m0755 "${pkgdir}/srv/avnsrv/updates"
  install -d -m0755 "${pkgdir}/srv/avnsrv/backups"
  install -d -m0755 "${pkgdir}/srv/avnsrv/logs"
  install -d -m0755 "${pkgdir}/srv/avnsrv/tmpfs"
  install -d -m0755 "${pkgdir}/srv/avnsrv/.config"
  install -d -m0755 "${pkgdir}/srv/avnsrv/.config/systemd"
  install -d -m0755 "${pkgdir}/srv/avnsrv/.config/systemd/user"
  install -D -Dm755 "${srcdir}/avnsrv-script.bash" "${pkgdir}/usr/bin/avnsrv-script"
  install -D -Dm755 "${srcdir}/avnsrv-timer-1.timer" "${pkgdir}/srv/avnsrv/.config/systemd/user/avnsrv-timer-1.timer"
  install -D -Dm755 "${srcdir}/avnsrv-timer-1.service" "${pkgdir}/srv/avnsrv/.config/systemd/user/avnsrv-timer-1.service"
  install -D -Dm755 "${srcdir}/avnsrv-timer-2.timer" "${pkgdir}/srv/avnsrv/.config/systemd/user/avnsrv-timer-2.timer"
  install -D -Dm755 "${srcdir}/avnsrv-timer-2.service" "${pkgdir}/srv/avnsrv/.config/systemd/user/avnsrv-timer-2.service"
  install -D -Dm755 "${srcdir}/avnsrv-send-notification@.service" "${pkgdir}/srv/avnsrv/.config/systemd/user/avnsrv-send-notification@.service"
  install -D -Dm755 "${srcdir}/avnsrv@.service" "${pkgdir}/srv/avnsrv/.config/systemd/user/avnsrv@.service"
  install -D -Dm755 "${srcdir}/avnsrv-mkdir-tmpfs@.service" "${pkgdir}/srv/avnsrv/.config/systemd/user/avnsrv-mkdir-tmpfs@.service"
  install -D -Dm755 "${srcdir}/avnsrv-tmpfs@.service" "${pkgdir}/srv/avnsrv/.config/systemd/user/avnsrv-tmpfs@.service"
  install -D -Dm755 "${srcdir}/bash_profile" "${pkgdir}/srv/avnsrv/.bash_profile"
}
