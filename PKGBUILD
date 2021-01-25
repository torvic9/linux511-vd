# Based on the file created for Arch Linux by:
# Tobias Powalowski <tpowa@archlinux.org>
# Thomas Baechler <thomas@archlinux.org>

# Maintainer (vd): torvic9

pkgbase=linux511-vd
pkgname=('linux511-vd' 'linux511-vd-headers')
_basekernel=5.11
_kernelname=-vd
_sub=0
_rc=rc5
pkgver=${_basekernel}.${_sub}${_rc}
pkgrel=1
_archpatch=20210124
_prjc="r2"
_stablequeue=a1028684e3
arch=('x86_64')
url="http://www.kernel.org/"
license=('GPL2')
makedepends=('xmlto' 'docbook-xsl' 'kmod' 'inetutils' 'bc' 'elfutils' 'git' 'libelf')
options=('!strip')
source=(https://git.kernel.org/torvalds/t/linux-${_basekernel}-${_rc}.tar.gz
    #https://cdn.kernel.org/pub/linux/kernel/v5.x/linux-${pkgver}.tar.{xz,sign}
    # the main kernel config files
    'config.x86_64' 'config.x270' 'config.zen2' 'x509.genkey' "${pkgbase}.preset"
    #
    # Prepatch from stable-queue
    # "prepatch-${_basekernel/./}-g${_stablequeue}.patch"
    #
    # Arch patches
    0001-arch-patches510-${_archpatch}.patch::https://raw.githubusercontent.com/sirlucjan/kernel-patches/master/5.11-rc/arch-patches-v5/0001-arch-patches.patch
    # CPU patches
    0002-graysky-cpu-optimizations.patch
    0003-enable-O3-for-all-archs-and-add-option-for-O1.patch
    # zstd 1.4.6 from terrelln
    0004-update-to-zstd-146-v7.patch
    # Clear Linux
    0005-clearlinux-tweak-intel-cpuidle.patch
    0006-clearlinux-add-config-opt-for-raid6-bench.patch
    # AMD enhancements
    0007-dma-add-support-for-amd-ptdma-controller-driver.patch
    0008-acpi-add-processor-to-the-ignore-PSD-override-list.patch
    # bfq fixes
    0009-block-bfq-fixes-and-improvements.patch
    # tip:sched/core
    0010-tip-sched-core-20210114.patch
    # sched idle
    0011-sched-scan-for-an-idle-sibling-in-a-single-pass.patch
    # Nuvoton nc677x driver
    0012-i2c-nuvoton-nc677x-hwmon-driver-git.patch::https://gitlab.com/CalcProgrammer1/OpenRGB/-/raw/master/OpenRGB.patch
    # rcu fixes
    0013-rcu-fixes-next.patch
    # rcu fix prio boost
    0014-fix-rcu-priority-boosting.patch
    # blk-mq fixes
    0015-blk-mq-dont-complete-in-IRQ-use-llist_head.patch
    # amd sensor fusion hub
    0016-amd-sfh-driver-refactored.patch
    #
    # futex_wait_multiple
    1001-futex-futex_wait_multiple-krisman.patch
    # 1001-futex-valve-integ-20201126.patch
    # 1002-futex2-stable.patch # we do not yet need this
    #
    # MANJARO Patches
    #
    # vd/hho patches
    2001-add-acpi_call-module.patch
    2002-tune-vm-mm-and-vfs-settings.patch
    2003-tune-cfs-settings.patch
    2004-allow-cpufreq-ondemand-with-muqss-and-projectc.patch
    2005-tune-cpufreq-ondemand-settings.patch
    2006-optimise-kernel-and-module-compression.patch
    # ntfs3 driver
    2007-ntfs-rw-gpl-driver-implementation-by-paragon-v18.patch::https://raw.githubusercontent.com/sirlucjan/kernel-patches/master/5.11-rc/ntfs3-patches-v2/0001-ntfs3-patches.patch
    #
    # Project C (BMQ+PDS)
    # 3001-projectc510-${_prjc}-orig.patch::https://gitlab.com/alfredchen/linux-prjc/uploads/cda220f104bd6e07ea6fefa86c709dbe/prjc_v5.10-r2.patch
    # CacULE
    # 3002-cacule-510rdb.patch::https://raw.githubusercontent.com/hamadmarri/cacule-cpu-scheduler/master/patches/CacULE/v5.10/cacule5.10-rdb.patch
    # MuQSS
    # 3003-ck-muqss-510.patch
    #
    # pgo profile data
    # vmlinux.profdata
)

validpgpkeys=(
  'ABAF11C65A2970B130ABE3C479BE3E4300411886'  # Linus Torvalds
  '647F28654894E3BD457199BE38DBBDC86092693E'  # Greg Kroah-Hartman
)

sha256sums=('9864eb2880ffab9b776be9f6f222015165a23d1303619a3e2ed5671b88be3609'
            '29dd0f29a8001f9cf1062ee78e1e84ad7845fa0bd319dcab7ab9c5c7cb74c07c'
            'afaa3d41e954f0ccd79ab63a57d459caef339de437fba8c01152d1c1d6a31bc7'
            '09c81b7a8a74f7c4bcd775f28368a1d2bcae4792a7972dd7b728d132b0f04295'
            'ab010dc5ef6ce85d352956e5996d242246ecd0912b30f0b72025c38eadff8cd5'
            '8f357fab1c5b3e81240b543a6643fdbca1d8591f5dd18bc18e38ae992d78944c'
            '8b00e83ec9b288cf308b435de432a618649ef8fc9b083f5770b7627c5772800d'
            '9b0c200b0dadfcfb1b3c42acd0c007e1d582a86abc6b04f3096e0535c8784ab6'
            '3d38fc4052b999b67aaed9fe9a4ba6ffd778ffbf7e94a66d5577391dbd08d12a'
            '0a05bbb282502db210f8ab843a5c3f39b847af5303fb7bd5a8655686cf76c1b7'
            'b78ab97a629579ebc27ff175eacc9162a07c9b925cebd91099c97ef509bd117d'
            'b817e7da8f4901cf2dda0f2fe7b9d8243f32a42d5729e953521ef18eec7a8eb9'
            '1f47d3e3956c41b47656f675a90fad9e318c7133ffe663dc0fd2c9aa0fbfeb3e'
            '5000348583882523ef3c36df27eabf4355e83d0605081a3bf5d4aaa28e518162'
            'e96d2466ff31dd4555a9166bcbe5a2482e217a6ae7c66027180ccdf66eee872f'
            '9c8e25fbe47e3989fdb1864e4786e3a09d9956c10af357669e891ae2157f9915'
            '03022ad0414ee728d1cc51a7b23997beb46d8d7f53ce1773ec94cee198d8fcc1'
            'e7d724ac15daf428aa1e6a03737e5c1d040892d55fda8a66897fcac9323f285c'
            'a652bf7985cd0633ee12e61efb9dd898f28468e93caa852e210923fed92724fb'
            '49b29307ee96f85db5949866fd2f5a76502dd5be7564771febfe57c807b4f740'
            '12fdebdffb9ba9620a012eafba79162d83d13700a47af5b9feef4d91e9600d6f'
            'a881179be827dfee0b10c704fc8e1c501683f61e8041df392b48b51cba215856'
            'b86758554105a11900e60b1f83bd272aee8ce3af5c62a382160637844ee4f2a5'
            '7fd689f4ec88364d1ac00007e6f1e273ee9b53cae187e0f70e7f810303dc9303'
            'f7a36231b794022d49e53f464d25e48f2eebf6266c2cbe5756c63aa3bf03bae7'
            'acca50a9ffee480f29bd7de6e8b5963dc0d37d3103871d75bcffdb2acce6c82d'
            '4c0beb1f181e7ee22e978f447aaccc3bd7f326e861a5afb5798922b1e7efc2ec'
            '02d2c0e6b2459d4dbd6d4cecb3b269545a78b86cc9d2d3a0fda80bb3c3ee7604'
            'a231aebaa262c60f5f0151819db4b06e92986d5c81e8e0a90e7089a0ac9d454c'
            'd3d92b1ee6ea952c368a6b806d78a35ea400255a6abe9a0f6c24a45ecbfb90a1')

export KBUILD_BUILD_USER=$pkgbase
export KBUILD_BUILD_HOST=eos
export KBUILD_BUILD_TIMESTAMP="$(date -Ru${SOURCE_DATE_EPOCH:+d @$SOURCE_DATE_EPOCH})"

# signing
_signing=0
# edit the paths below to point to your signing keys
_key="$HOME/build/keys/vd511-kernel-key.pem"
_pubkey="$HOME/build/keys/vd511-kernel-pubkey.pem"

# custom clang path
# export PATH=/opt/clang11/bin:$PATH
_clang=0

if [[ ${_clang} -eq 1 ]]; then
	LLVMOPTS="LLVM=1 LLVM_IAS=1"
	CLANGOPTS="CC=clang LD=ld.lld"
	source+=('9001-objtool-fixes-jp.patch'
	'9002-clang-lto-20210123.patch'
	#'9003-clang-pgo-v6.patch' # pgo is still very experimental
	)
	sha256sums+=('6facba496859c28160d5872800834af28fb152feaf07d4cfa03cf1fc611bcd67'
	'c8f09c8449b7248bbdbaf749a114803026c3ccd5e2dc207c0b412a4d5537647f'
	#'5b051af3ad9235268c40c60d1d5986ee49d97b7ccf7c13668d57c9a1cefa197b'
	)
else
	LLVMOPTS=""
	CLANGOPTS=""
fi

TB=$(tput bold)
TN=$(tput sgr0)

prepare() {

  cd "${srcdir}/linux-${_basekernel}-${_rc}"

  echo "-${_kernelname/-/}" > localversion.10-pkgname
  echo "-${pkgrel}" > localversion.20-pkgrel

  echo -e "\n${TB}* APPLYING PATCHES${TN}"

  # apply patch from the source array (should be a pacman feature)
  local filename filename2
  for filename in "${source[@]}"; do
  	if [[ "$filename" =~ \.patch$ || "$filename" =~ \.diff$ ]]; then
		filename="${filename%%::*}"
		filename2="${filename#*-}"
        	echo -e "\n---- Applying patch ${TB}${filename2%%.*}${TN}:"
        	patch -Np1 -i "../${filename}"
  	fi
  done

  # kernel config
  echo -e "\n${TB}* KERNEL CONFIGURATION${TN}"
  local _config
  echo "---- Select configuration file:"
  echo "${TB}1)${TN} Default"
  echo "${TB}2)${TN} Zen2"
  echo "${TB}3)${TN} X270"
  while true ; do
  	read -p "Enter number (1-3): " _config
	  case ${_config} in
		1) cat ../config.x86_64 > ./.config && break ;;
		2) cat ../config.zen2 > ./.config && break ;;
		3) cat ../config.x270 > ./.config && break ;;
		*) echo "Please enter a number (1-3)!" && continue ;;
  	  esac
  done

  if [[ ${_signing} -eq 1 ]] ; then
    cat ${_key} > ./certs/vd511-kernel-key.pem
    cat ${_pubkey} > ./certs/vd511-kernel-pubkey.pem
    sed -i "s|signing_key|vd511-kernel-key|" ./.config
    sed -ri "s|^(CONFIG_SYSTEM_TRUSTED_KEYS=).*|\1\"certs/vd511-kernel-pubkey.pem\"|" ./.config
  else
    cat ../x509.genkey > ./certs/x509.genkey
  fi

  # get kernel version
  make $LLVMOPTS prepare
  make $LLVMOPTS -s kernelrelease > version
  printf '\n'
  printf "  Prepared %s version %s" "$pkgbase" "$(<version)"
  printf '\n'
  read -p "---- Enter 'y' for nconfig: " NCONFIG
  [[ $NCONFIG = "y" ]] && make $LLVMOPTS nconfig || continue

  # rewrite configuration
  yes '' | make $LLVMOPTS config >/dev/null
}

build() {
  cd "${srcdir}/linux-${_basekernel}-${_rc}"
  
  # copy pgo profile data
  # cp $srcdir/vmlinux.profdata ./
  
  # build!
  make $LLVMOPTS LOCALVERSION= bzImage modules
  # below cmd is for using a pgo profile
  # make $LLVMOPTS KCFLAGS=-fprofile-use=vmlinux.profdata LOCALVERSION= bzImage modules
}

package_linux511-vd() {
  pkgdesc="The ${pkgbase/linux/Linux} vd kernel and modules"
  depends=('coreutils' 'linux-firmware' 'kmod' 'mkinitcpio>=27')
  optdepends=('crda: to set the correct wireless channels of your country')
  provides=(VIRTUALBOX-GUEST-MODULES)
  replaces=(linux510-vd-virtualbox-guest-modules)

  cd "${srcdir}/linux-${_basekernel}-${_rc}"

  local kernver="$(<version)"
  local modulesdir="$pkgdir/usr/lib/modules/$kernver"

  mkdir -p "${pkgdir}"/{boot,usr/lib/modules}

  # systemd expects to find the kernel here to allow hibernation
  # https://github.com/systemd/systemd/commit/edda44605f06a41fb86b7ab8128dcf99161d2344
  install -Dm644 "$(make $CLANGOPTS -s image_name)" "$modulesdir/vmlinuz"

  # Used by mkinitcpio to name the kernel
  echo "${pkgbase}" | install -Dm644 /dev/stdin "$modulesdir/pkgbase"
  #echo "${kernelbase}-${CARCH}" | install -Dm644 /dev/stdin "$modulesdir/kernelbase"

  # make room for external modules
  local _extramodules="extramodules-${pkgbase}"
  ln -s "../${_extramodules}" "$modulesdir/extramodules"
  # add real version for building modules and running depmod from hook
  echo "${kernver}" |
    install -Dm644 /dev/stdin "${pkgdir}/usr/lib/modules/${_extramodules}/version"

  echo -e "\n${TB}* INSTALLING MODULES${TN}"
  make $CLANGOPTS LOCALVERSION= INSTALL_MOD_PATH="${pkgdir}/usr" INSTALL_MOD_STRIP=1 modules_install
  # do not strip when building a pgo kernel
  # make $CLANGOPTS LOCALVERSION= INSTALL_MOD_PATH="${pkgdir}/usr" modules_install

  # remove build and source links
  rm $modulesdir/source
  rm $modulesdir/build
  [[ -f ./certs/vd511-kernel-key.pem ]] && rm ./certs/vd511-kernel-key.pem

  # add mkinitcpio preset (not strictly needed)
  install -Dm644 "$srcdir/${pkgbase}.preset" "$pkgdir/etc/mkinitcpio.d/${pkgbase}.preset"
}

package_linux511-vd-headers() {
  pkgdesc="Header files and scripts for building modules for ${pkgbase/linux/Linux} vd kernel"

  cd "${srcdir}/linux-${_basekernel}-${_rc}"
  local kernver="$(<version)"
  local _builddir="${pkgdir}/usr/lib/modules/${kernver}/build"

  echo -e "\n${TB}* INSTALLING HEADERS${TN}"
  install -Dt "${_builddir}" -m644 Makefile .config Module.symvers System.map version vmlinux localversion.* || exit 32
  install -Dt "${_builddir}/kernel" -m644 kernel/Makefile
  install -Dt "${_builddir}/arch/x86" -m644 "arch/x86/Makefile"
  #mkdir "${_builddir}/.tmp_versions"

  cp -t "${_builddir}" -a include scripts

  # add objtool for external module building and enabled VALIDATION_STACK option
  install -Dt "${_builddir}/tools/objtool" tools/objtool/objtool

  # add xfs and shmem for aufs building
  mkdir -p "${_builddir}"/{fs/xfs,mm}

  cp -t "${_builddir}/arch/x86" -a "arch/x86/include"
  install -Dt "${_builddir}/arch/x86/kernel" -m644 "arch/x86/kernel/asm-offsets.s"
  #install -Dt "${_builddir}/arch/${KARCH}/kernel" -m644 "arch/${KARCH}/kernel/macros.s"

  install -Dt "${_builddir}/drivers/md" -m644 drivers/md/*.h
  install -Dt "${_builddir}/net/mac80211" -m644 net/mac80211/*.h

  # http://bugs.archlinux.org/task/13146
  install -Dt "${_builddir}/drivers/media/i2c" -m644 drivers/media/i2c/msp3400-driver.h

  # http://bugs.archlinux.org/task/20402
  install -Dt "${_builddir}/drivers/media/usb/dvb-usb" -m644 drivers/media/usb/dvb-usb/*.h
  install -Dt "${_builddir}/drivers/media/dvb-frontends" -m644 drivers/media/dvb-frontends/*.h
  install -Dt "${_builddir}/drivers/media/tuners" -m644 drivers/media/tuners/*.h

  # copy in Kconfig files
  find . -name Kconfig\* -exec install -Dm644 {} "${_builddir}/{}" \;

  # remove unneeded stuff
  echo -e "\n${TB}* REMOVING UNNEEDED FILES${TN}"
  # remove unneeded architectures
  local _arch
  for _arch in "${_builddir}"/arch/*/; do
    [[ ${_arch} == */x86/ ]] && continue
    rm -r "${_arch}"
  done

  # remove files already in linux-docs package
  rm -r "${_builddir}/Documentation"

  # remove broken symlinks
  find -L "${_builddir}" -type l -printf 'Removing %P\n' -delete

  # remove loose objects"
  find "${_builddir}" -type f -name '*.o' -printf 'Removing %P\n' -delete

  # strip scripts directory
  echo -e "\n${TB}* STRIPPING${TN}"
  local file
  while read -rd '' file; do
    case "$(file -bi "$file")" in
      application/x-sharedlib\;*)      # Libraries (.so)
        strip -v $STRIP_SHARED "$file" ;;
      application/x-archive\;*)        # Libraries (.a)
        strip -v $STRIP_STATIC "$file" ;;
      application/x-executable\;*)     # Binaries
        strip -v $STRIP_BINARIES "$file" ;;
      application/x-pie-executable\;*) # Relocatable binaries
        strip -v $STRIP_SHARED "$file" ;;
    esac
  done < <(find "${_builddir}" -type f -perm -u+x ! -name vmlinux -print0)
  
  strip -v $STRIP_STATIC "${_builddir}/vmlinux"
}
