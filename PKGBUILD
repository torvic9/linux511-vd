# Based on the file created for Arch Linux by:
# Tobias Powalowski <tpowa@archlinux.org>
# Thomas Baechler <thomas@archlinux.org>

# Maintainer (vd): torvic9

pkgbase=linux511-vd
pkgname=('linux511-vd' 'linux511-vd-headers')
_basekernel=5.11
_kernelname=-vd
_sub=4
#_rc=rc7
pkgver=${_basekernel}.${_sub}
pkgrel=2
_archpatch=20210301
_prjc="r1"
_stablequeue=7f889ae426
arch=('x86_64')
url="http://www.kernel.org/"
license=('GPL2')
makedepends=('xmlto' 'docbook-xsl' 'kmod' 'inetutils' 'bc' 'elfutils' 'git' 'libelf')
options=('!strip')
source=(https://cdn.kernel.org/pub/linux/kernel/v5.x/linux-${pkgver}.tar.{xz,sign}
    #https://git.kernel.org/torvalds/t/linux-${_basekernel}-${_rc}.tar.gz
    # the main kernel config files
    'config.x86_64' 'config.x270' 'config.zen2' 'x509.genkey' "${pkgbase}.preset"
    #
    # Prepatch from stable-queue
    "prepatch-${_basekernel/./}-g${_stablequeue}.patch"
    #
    # Arch patches
    # 0001-arch-patches511-${_archpatch}.patch::https://raw.githubusercontent.com/sirlucjan/kernel-patches/master/5.11/arch-patches-v5/0001-arch-patches.patch
    0001-arch-patches511-${_archpatch}.patch
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
    0009-amd-sfh-driver-refactored.patch
    # blk-mq fixes
    0010-blk-mq-dont-complete-in-IRQ-use-llist_head.patch
    0011-blk-mq-improve-performance-of-non-mq-io-schedulers.patch
    # bfq fixes
    0012-block-bfq-fixes-and-improvements.patch
    # tip:sched/core
    0013-tip-sched-core-20210305.patch
    # 0013-tip-sched-core-no-dyn-preempt-20210305.patch # for use with ProjectC
    # rcu fixes
    0014-rcu-fixes-next.patch
    # rcu fix prio boost
    0015-rcu-fix-priority-boosting.patch
    # amdgpu
    0016-drm-amdgpu-fixes-next.patch
    # fs buffer fix
    0017-fs-buffer-revoke-lru-when-trying-to-drop-buffers-v4.patch
    # btrfs patches
    # 0019-btrfs-patches-sirlucjan.patch::https://raw.githubusercontent.com/sirlucjan/kernel-patches/master/5.11/btrfs-patches-v3/0001-btrfs-patches.patch
    0018-btrfs-patches-sirlucjan.patch
    # multigenerational lru by google
    0019-multigenerational-lru-v1.patch
    # Nuvoton nc677x driver
    0020-i2c-nuvoton-nc677x-hwmon-driver-git.patch::https://gitlab.com/CalcProgrammer1/OpenRGB/-/raw/master/OpenRGB.patch
    # async initramfs unpacking
    0021-init-initramfs.c-allow-asynchronous-unpacking.patch
    # hrtimer fix
    0022-hrtimer-softirq-fix.patch
    #
    # futex_wait_multiple
    1001-futex-sirlucjan.patch::https://raw.githubusercontent.com/sirlucjan/kernel-patches/master/5.11/futex-trunk-patches/0001-futex-resync-from-gitlab.collabora.com.patch
    #1002-futex2-511.patch # we cannot use this yet ootb, needs patched glibc+systemd+wine
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
    2007-ntfs-rw-gpl-driver-implementation-by-paragon-v21.patch
    # kcpuid tool
    2008-tools-x86-add-kcpuid.patch
    #
    # Project C (BMQ+PDS)
    # 3001-projectc511-${_prjc}-orig.patch::https://gitlab.com/alfredchen/linux-prjc/uploads/604a80e2e5ac99c431f0944e4e986aa6/prjc_v5.11-r1.patch
    # 3001-projectc511-${_prjc}-vd.patch # for use with tip
    # CacULE
    #
    # pgo profile data
    # vmlinux.profdata
    #
    # reverts
    sched-fair-update_pick_idlest.revert
    # clang
    9001-objtool-fixes-jp.patch
    9002-clang-lto-20210217.patch
    # 9003-clang-pgo-v7.patch # pgo is still very experimental
    # speed improvement with trim_unused_ksyms, with needed patches from next
    9004-kbuild-build-speed-improvment-of-trim_unused_ksyms.patch
)

validpgpkeys=(
  'ABAF11C65A2970B130ABE3C479BE3E4300411886'  # Linus Torvalds
  '647F28654894E3BD457199BE38DBBDC86092693E'  # Greg Kroah-Hartman
)

sha256sums=('88e59fafc9653cb7eef501cef3eda677843027735fd11325a75e353b10770dc5'
            'SKIP'
            'f2b7a8cf91c49a68e20c8ec8013c3e852348defeb55172a31ec6558f20da49c9'
            '9afa4aa97b7b0c4116a5cc8716a65a1289407d96bf3adc78b73d9197a9c39fa9'
            '512f401d95d6612aa050285dcd3c495af0031d313488824f56f9d21ce03c5490'
            'ab010dc5ef6ce85d352956e5996d242246ecd0912b30f0b72025c38eadff8cd5'
            '8f357fab1c5b3e81240b543a6643fdbca1d8591f5dd18bc18e38ae992d78944c'
            'ea795e425d4a6e19d4a7d5a723bb572b6e3547e1f9499508b28cbcb544066ce9'
            '8c8f0080e5ecbb3b4982e288d3393dedfc7001227753983e128318b23ca117fa'
            '9b0c200b0dadfcfb1b3c42acd0c007e1d582a86abc6b04f3096e0535c8784ab6'
            '3d38fc4052b999b67aaed9fe9a4ba6ffd778ffbf7e94a66d5577391dbd08d12a'
            '0a05bbb282502db210f8ab843a5c3f39b847af5303fb7bd5a8655686cf76c1b7'
            'b78ab97a629579ebc27ff175eacc9162a07c9b925cebd91099c97ef509bd117d'
            'b817e7da8f4901cf2dda0f2fe7b9d8243f32a42d5729e953521ef18eec7a8eb9'
            '1f47d3e3956c41b47656f675a90fad9e318c7133ffe663dc0fd2c9aa0fbfeb3e'
            '5000348583882523ef3c36df27eabf4355e83d0605081a3bf5d4aaa28e518162'
            'a881179be827dfee0b10c704fc8e1c501683f61e8041df392b48b51cba215856'
            '18a84957915dd924cbdddfb031954f97e951bd96f5593fb1eb8c73bc4a61bd3f'
            '623a3b02b980fcd52bc7d230be1661ada7b557e3cd83c0560666e1f010bd3509'
            '6409d37e9d10c3d66fee9c919e508c96044e370b7e094865aa83e94476769349'
            'ca02a2a5cbcbc62bb02b55165e3b5fc615f5fa7d7d1a725ece09015131f41157'
            'a652bf7985cd0633ee12e61efb9dd898f28468e93caa852e210923fed92724fb'
            '49b29307ee96f85db5949866fd2f5a76502dd5be7564771febfe57c807b4f740'
            'de04c29f815c0a2f9cac948c930c0933ec2a38b18367b327d3b626e96206a823'
            '1523298b9c29fa80ecc945982b7e450b5a9128054f91bce0fc596141ed3d1df2'
            '7ab8ac222da738405eee6919ccc97115afce7739714ce983d5f4f2755d59ada5'
            'ca2cd10fc86d3347d98da60e11b8ca02544d62d4da6179b9555fc92cacfb6838'
            'e7d724ac15daf428aa1e6a03737e5c1d040892d55fda8a66897fcac9323f285c'
            'ebb1cc8dd0bdcde7246aacee531d06a5b035ccd481f4c306f2316010a7be2282'
            'bc08a777a028c56a2ff576592820cec7aa574a2c30b747d365b4e9234bd32f85'
            '239307e0018ab2405b9afaa7d315ee3352b83819a3c75b65951749b52a3247d2'
            '7fd689f4ec88364d1ac00007e6f1e273ee9b53cae187e0f70e7f810303dc9303'
            'f7a36231b794022d49e53f464d25e48f2eebf6266c2cbe5756c63aa3bf03bae7'
            'acca50a9ffee480f29bd7de6e8b5963dc0d37d3103871d75bcffdb2acce6c82d'
            '4c0beb1f181e7ee22e978f447aaccc3bd7f326e861a5afb5798922b1e7efc2ec'
            '02d2c0e6b2459d4dbd6d4cecb3b269545a78b86cc9d2d3a0fda80bb3c3ee7604'
            '33752d734f2276e5f396da3512a7a7f47b8bb6037b70d17120fd5c30f807a8cd'
            '24a024268e8ac2548078ad7ea3445a2331d21df6eb01f5caf9b1b42caf4241bb'
            'a3feec582e3c575ff43f028f46c9c41cf1f5a1943955805613fdcd1c639bed57'
            'cd96250876c30af9a1b5a7f8191ab8390842c993bd92f6987fb661e3edf1941e'
            '4b6698dab016c6b76eae4c4fa107a6c13806bc0dbfd143a06cebd07561a4080f'
            'defe5d56d9d93aa785c4ba4fe5f2682c00a9a3fdb19fedeeeb95aae8261d8c0e'
            '3b59a65e179e79b7372c451bdaf8f41ccc336615e492340f7d65b00e12c49b3d')

export KBUILD_BUILD_USER=$pkgbase
export KBUILD_BUILD_HOST=eos
export KBUILD_BUILD_TIMESTAMP="$(date -Ru${SOURCE_DATE_EPOCH:+d @$SOURCE_DATE_EPOCH})"

# signing
_signing=0
# edit the paths below to point to your signing keys
_key="$HOME/build/keys/vd511-kernel-key.pem"
_pubkey="$HOME/build/keys/vd511-kernel-pubkey.pem"

# custom clang path
# export PATH=/opt/clang12/bin:$PATH
_clang=0

if [[ ${_clang} -eq 1 ]]; then
	LLVMOPTS="LLVM=1 LLVM_IAS=1"
	CLANGOPTS="CC=clang LD=ld.lld"
else
	LLVMOPTS=""
	CLANGOPTS=""
fi

TB=$(tput bold)
TN=$(tput sgr0)

prepare() {

  cd "${srcdir}/linux-${pkgver}"

  echo "-${_kernelname/-/}" > localversion.10-pkgname
  echo "-${pkgrel}" > localversion.20-pkgrel

  echo -e "\n${TB}* APPLYING PATCHES${TN}"

  echo -e "\n---- Reverts:" # add reverts here
  patch -Rp1 -i "../sched-fair-update_pick_idlest.revert"

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
  cd "${srcdir}/linux-${pkgver}"

  # copy pgo profile data
  # cp $srcdir/vmlinux.profdata ./

  # build!
  make $LLVMOPTS LOCALVERSION= bzImage modules
  make $CLANGOPTS -C tools/arch/x86/kcpuid
  # below cmd is for using a pgo profile, 1st without LTO, 2nd with LTO
  # make $LLVMOPTS KCFLAGS=-fprofile-use=vmlinux.profdata LOCALVERSION= bzImage modules
  # make $LLVMOPTS KCFLAGS=-lto-cs-profile-file=vmlinux.profdata LOCALVERSION= bzImage modules
}

package_linux511-vd() {
  pkgdesc="The ${pkgbase/linux/Linux} vd kernel and modules"
  depends=('coreutils' 'linux-firmware' 'kmod' 'mkinitcpio>=27')
  optdepends=('crda: to set the correct wireless channels of your country')
  provides=(VIRTUALBOX-GUEST-MODULES)
  replaces=(linux511-vd-virtualbox-guest-modules)

  cd "${srcdir}/linux-${pkgver}"

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

  cd "${srcdir}/linux-${pkgver}"
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

  # add kcpuid
  install -Dt "${_builddir}/tools/arch/x86/kcpuid" tools/arch/x86/kcpuid/kcpuid

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
