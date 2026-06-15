kaka@kaka-optplex:~/Desktop/ROS2_software_flashing_tool$ cd flashtool/Linux_for_Tegra
kaka@kaka-optplex:~/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra$ ls
apply_binaries.sh
bootloader
build_l4t_bup.sh
flash.sh
generate_capsule
igx-orin-devkit.conf
jetson_additional_board_spec.cfg
jetson-agx-orin-devkit-as-jao-32gb.conf
jetson-agx-orin-devkit-as-nano4gb.conf
jetson-agx-orin-devkit-as-nano8gb.conf
jetson-agx-orin-devkit-as-nx-16gb.conf
jetson-agx-orin-devkit-as-nx-8gb.conf
jetson-agx-orin-devkit.conf
jetson-agx-orin-devkit-industrial.conf
jetson-agx-orin-devkit-industrial-maxn.conf
jetson-agx-orin-devkit-industrial-qspi.conf
jetson-agx-orin-devkit-maxn.conf
jetson_board_spec.cfg
jetson-orin-nano-devkit.conf
jetson-orin-nano-devkit-nvme.conf
kernel
l4t_generate_soc_bup.sh
l4t_sign_image.sh
l4t_uefi_sign_image.sh
make_firmware_deb.sh
mk_ota_img.sh
nvautoflash.sh
nvmassfusegen.sh
nvsdkmanager_flash.sh
nv_tegra
nv_tools
odmfuse.func
odmfuseread.sh
odmfuse.sh
ota_update.sh
p3509-a02-p3767-0000.conf
p3701.conf.common
p3737-0000-p3701-0000-as-p3701-0004.conf
p3737-0000-p3701-0000-as-p3767-0000.conf
p3737-0000-p3701-0000-as-p3767-0001.conf
p3737-0000-p3701-0000-as-p3767-0003.conf
p3737-0000-p3701-0000-as-p3767-0004.conf
p3737-0000-p3701-0000.conf
p3737-0000-p3701-0000.conf.common
p3737-0000-p3701-0000-maxn.conf
p3737-0000-p3701-0000-qspi.conf
p3737-0000-p3701-0008.conf
p3737-0000-p3701-0008-maxn.conf
p3737-0000-p3701-0008-qspi.conf
p3740-0002-p3701-0008.conf
p3740-0002-p3701-0008-qspi.conf
p3767.conf.common
p3768-0000-p3767-0000-a0.conf
p3768-0000-p3767-0000-a0-maxn.conf
p3768-0000-p3767-0000-a0-nvme.conf
p3768-0000-p3767-0000-a0-qspi.conf
README_Autoflash.txt
rootfs
source
Tegra_Software_License_Agreement-Tegra-Linux.txt
tools
tztek_flash.sh
tztek-jetson-firmware-kernel-dtb-510jx0-r2.1-jp6.0.0-v6.0.3
tztek-jetson-firmware-kernel-dtb-510jx0-r3.0-jp6.0.0-v6.0.3
tztek_ota
TZTEK_OTA_ORIN_EMMC.conf
TZTEK_OTA_ORIN_SSD.conf
kaka@kaka-optplex:~/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra$ sudo ./tztek_flash.sh 
[sudo] password for kaka: 
====================================
    Welcome to tztek flash tool     
            v2.2.3                  
====================================
请输入烧录功能编号:
1.kernel  2.dtb  3.initrd-backup  4.bct-pinmux  5.massflash  6.without-no-flash  7.flash-all  8.flash-all-with-system  9.Initrd-mode
number:7
======= flash-all


请输入平台型号编号:
1.xavier  2.nx-emmc  3.nx-sdcard  4.tx2-8g  5.tx2-4g  6.agx_orin  7.orin_nx_nano  8.agx_orin_nvme
number:8


------- sudo ADDITIONAL_DTB_OVERLAY_OPT="BootOrderNvme.dtbo," ./tools/kernel_flash/l4t_initrd_flash.sh --external-device nvme0n1p1 -c tools/kernel_flash/flash_l4t_external.xml -p "-c bootloader/generic/cfg/flash_t234_qspi.xml --no-systemimg" --network usb0 jetson-agx-orin-devkit nvme0n1p1 
(yes/no, default is yes):yes
/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/l4t_initrd_flash_internal.sh --no-flash --external-device nvme0n1p1 -c tools/kernel_flash/flash_l4t_external.xml -p -c bootloader/generic/cfg/flash_t234_qspi.xml --no-systemimg --network usb0 jetson-agx-orin-devkit nvme0n1p1
************************************
*                                  *
*  Step 1: Generate flash packages *
*                                  *
************************************
Create folder to store images to flash
Generate image for internal storage devices
Generate images to be flashed
ADDITIONAL_DTB_OVERLAY="BootOrderNvme.dtbo,"  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/flash.sh --no-flash --sign  -c bootloader/generic/cfg/flash_t234_qspi.xml --no-systemimg jetson-agx-orin-devkit nvme0n1p1

###############################################################################
# L4T BSP Information:
# R36 , REVISION: 3.0
# User release: 0.0
###############################################################################
ECID is 0x80012344705DF1172C0000000D020080
Existing emcfuse(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/fuse_t234.xml) reused.
copying emc_fuse_dev_params(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-br-bct-diag-boot.dts)... done.
copying device_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-device-p3701-0000.dts)... done.
copying misc_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-misc-p3701-0000.dts)... done.
./tegraflash.py --chip "0x23" --applet "/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/mb1_t234_prod.bin" --skipuid --cfg readinfo_t234_min_prod.xml --dev_params tegra234-br-bct-diag-boot.dts --device_config tegra234-mb1-bct-device-p3701-0000.dts --misc_config tegra234-mb1-bct-misc-p3701-0000.dts --bins "mb2_applet applet_t234.bin" --cmd "readfuses fuse_t234.bin fuse_t234.xml; dump eeprom cvm cvm.bin; dump try_custinfo custinfo_out.bin; reboot recovery" 
Welcome to Tegra Flash
version 1.0.0
Type ? or help for help and q or quit to exit
Use ! to execute system commands
 
[   0.0462 ] Reading fuses
[   0.0466 ] tegrarcm_v2 --chip 0x23 0 --ismb2applet
[   0.0468 ] File rcm_state open failed
[   0.0471 ] ERROR: failed to read rcm_state
[   0.0471 ] 
[   0.0784 ] tegrasign_v3.py --key None --getmode mode.txt
[   0.0785 ] Assuming zero filled SBK key
[   0.0473 ] Pre-processing config: tegra234-mb1-bct-device-p3701-0000.dts
[   0.2863 ] Pre-processing config: tegra234-mb1-bct-misc-p3701-0000.dts
[   0.3097 ] Parsing partition layout
[   0.3185 ] tegraparser_v2 --pt readinfo_t234_min_prod.xml.tmp
[   0.3248 ] Kernel DTB used: None
[   0.3248 ] WARNING: dce base dtb is not provided

[   0.3248 ] Parsing partition layout
[   0.3250 ] tegraparser_v2 --pt readinfo_t234_min_prod.xml.tmp
[   0.3253 ] Creating list of images to be signed
[   0.3367 ] tegrahost_v2 --chip 0x23 0 --partitionlayout readinfo_t234_min_prod.xml.bin --list images_list.xml zerosbk
[   0.3368 ] MB1: Nvheader already present is mb1_t234_prod_aligned.bin
[   0.3539 ] Header already present for mb1_t234_prod_aligned_sigheader.bin
[   0.3542 ] MB1: Nvheader already present is mb1_t234_prod_aligned.bin
[   0.3576 ] Header already present for mb1_t234_prod_aligned_sigheader.bin
[   0.3587 ] MB1: Nvheader already present is psc_bl1_t234_prod_aligned.bin
[   0.3729 ] Header already present for psc_bl1_t234_prod_aligned_sigheader.bin
[   0.3730 ] adding BCH for mb2_t234_aligned.bin
[   0.3805 ] MB1: Nvheader already present is psc_bl1_t234_prod_aligned.bin
[   0.3861 ] Header already present for psc_bl1_t234_prod_aligned_sigheader.bin
[   0.3862 ] adding BCH for mb2_t234_aligned.bin
[   0.3937 ] Filling MB1 storage info
[   0.3937 ] Parsing dev params for multi chains
[   0.3983 ] Generating br-bct
[   0.4092 ] Updating dev and MSS params in BR BCT
[   0.4092 ] tegrabct_v2 --dev_param tegra234-br-bct-diag-boot_cpp.dtb --brbct br_bct.cfg --chip 0x23 0
[   0.4278 ] Updating bl info
[   0.4280 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updateblinfo readinfo_t234_min_prod.xml.bin
[   0.4281 ] WARNING: boot chain is not completed. set to 0
[   0.4287 ] Generating signatures
[   0.4600 ] tegrasign_v3.py --key None --list images_list.xml --pubkeyhash pub_key.key --sha sha512
[   0.4601 ] Assuming zero filled SBK key
[   0.5220 ] Warning: pub_key.key is not found
[   0.4909 ] Parsing dev params for multi chains
[   0.4909 ] Generating br-bct
[   0.4911 ] Updating dev and MSS params in BR BCT
[   0.4911 ] tegrabct_v2 --dev_param tegra234-br-bct-diag-boot_cpp.dtb --brbct br_bct.cfg --chip 0x23 0
[   0.4915 ] Updating bl info
[   0.4917 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updateblinfo readinfo_t234_min_prod.xml.bin --updatesig images_list_signed.xml
[   0.4918 ] WARNING: boot chain is not completed. set to 0
[   0.5294 ] Generating SHA2 Hash
[   0.5622 ] Sha saved in br_bct_BR.sha
[   0.5310 ] Get Signed section of bct
[   0.5312 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --listbct bct_list.xml
[   0.5317 ] Signing BCT
[   0.5630 ] tegrasign_v3.py --key None --list bct_list.xml --pubkeyhash pub_key.key --sha sha512
[   0.5631 ] Assuming zero filled SBK key
[   0.5648 ] Sha saved in br_bct_BR.sha
[   0.5649 ] Warning: pub_key.key is not found
[   0.5337 ] Updating BCT with signature
[   0.5339 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updatesig bct_list_signed.xml
[   0.5342 ] Offset :4608 Len :3584
[   0.5347 ] Generating SHA2 Hash
[   0.5660 ] tegrasign_v3.py --key None --list bct_list.xml --sha sha512
[   0.5661 ] Assuming zero filled SBK key
[   0.5661 ] Assuming zero filled SBK key
[   0.5677 ] Sha saved in br_bct_BR.sha
[   0.5366 ] Updating BCT with SHA2 Hash
[   0.5368 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updatesha bct_list_signed.xml
[   0.5370 ] Offset :4608 Len :3584
[   0.5373 ] Offset :68 Len :8124
[   0.5376 ] Generating coldboot mb1-bct
[   0.5379 ] tegrabct_v2 --chip 0x23 0 --mb1bct mb1_cold_boot_bct.cfg --misc tegra234-mb1-bct-misc-p3701-0000_cpp.dtb --device tegra234-mb1-bct-device-p3701-0000_cpp.dtb
[   0.5381 ] MB1-BCT version: 0.13

[   0.5400 ] Parsing config file :tegra234-mb1-bct-device-p3701-0000_cpp.dtb 
[   0.5401 ] Added Platform Config 9 data with size :- 100
[   0.5402 ] Updating mb1-bct with firmware information
[   0.5404 ] tegrabct_v2 --chip 0x23 0 --mb1bct mb1_cold_boot_bct_MB1.bct --updatefwinfo readinfo_t234_min_prod.xml.bin
[   0.5414 ] tegrahost_v2 --chip 0x23 0 --align mb1_cold_boot_bct_MB1_aligned.bct
[   0.5416 ] Generating SHA2 Hash for mb1bct
[   0.5733 ] Sha saved in mb1_cold_boot_bct_MB1_aligned.sha
[   0.5738 ] Sha saved in mb1_cold_boot_bct_MB1.sha
[   0.5427 ] tegrahost_v2 --chip 0x23 0 --magicid MBCT --appendsigheader mb1_cold_boot_bct_MB1_aligned.bct zerosbk
[   0.5429 ] adding BCH for mb1_cold_boot_bct_MB1_aligned.bct
[   0.5748 ] tegrasign_v3.py --key None --list mb1_cold_boot_bct_MB1_aligned_sigheader.bct_list.xml --pubkeyhash pub_key.key --sha sha512
[   0.5749 ] Assuming zero filled SBK key
[   0.5759 ] Warning: pub_key.key is not found
[   0.5449 ] tegrahost_v2 --chip 0x23 0 --updatesigheader mb1_cold_boot_bct_MB1_aligned_sigheader.bct.encrypt mb1_cold_boot_bct_MB1_aligned_sigheader.bct.hash zerosbk
[   0.5456 ] Generating recovery mb1-bct
[   0.5458 ] tegrabct_v2 --chip 0x23 0 --mb1bct mb1_bct.cfg --misc tegra234-mb1-bct-misc-p3701-0000_cpp.dtb --device tegra234-mb1-bct-device-p3701-0000_cpp.dtb
[   0.5460 ] MB1-BCT version: 0.13

[   0.5475 ] Parsing config file :tegra234-mb1-bct-device-p3701-0000_cpp.dtb 
[   0.5476 ] Added Platform Config 9 data with size :- 100
[   0.5477 ] Updating mb1-bct with firmware information
[   0.5479 ] tegrabct_v2 --chip 0x23 0 --mb1bct mb1_bct_MB1.bct --recov --updatefwinfo readinfo_t234_min_prod.xml.bin
[   0.5501 ] tegrahost_v2 --chip 0x23 0 --align mb1_bct_MB1_aligned.bct
[   0.5504 ] Generating SHA2 Hash for mb1bct
[   0.5822 ] Sha saved in mb1_bct_MB1_aligned.sha
[   0.5826 ] Sha saved in mb1_bct_MB1.sha
[   0.5515 ] tegrahost_v2 --chip 0x23 0 --magicid MBCT --appendsigheader mb1_bct_MB1_aligned.bct zerosbk
[   0.5516 ] adding BCH for mb1_bct_MB1_aligned.bct
[   0.5835 ] tegrasign_v3.py --key None --list mb1_bct_MB1_aligned_sigheader.bct_list.xml --pubkeyhash pub_key.key --sha sha512
[   0.5837 ] Assuming zero filled SBK key
[   0.5847 ] Warning: pub_key.key is not found
[   0.5537 ] tegrahost_v2 --chip 0x23 0 --updatesigheader mb1_bct_MB1_aligned_sigheader.bct.encrypt mb1_bct_MB1_aligned_sigheader.bct.hash zerosbk
[   0.5543 ] Info: Skip generating mem_bct because sdram_config is not defined
[   0.5543 ] Info: Skip generating mem_bct because sdram_config is not defined
[   0.5543 ] Copying signatures
[   0.5546 ] tegrahost_v2 --chip 0x23 0 --partitionlayout readinfo_t234_min_prod.xml.bin --updatesig images_list_signed.xml
[   0.5595 ] mb1_t234_prod_aligned_sigheader.bin.encrypt filename is from images_list
[   0.5597 ] psc_bl1_t234_prod_aligned_sigheader.bin.encrypt filename is from images_list
[   0.5597 ] Boot Rom communication
[   0.5600 ] tegrarcm_v2 --new_session --chip 0x23 0 --uid --download bct_br br_bct_BR.bct --download mb1 mb1_t234_prod_aligned_sigheader.bin.encrypt --download psc_bl1 psc_bl1_t234_prod_aligned_sigheader.bin.encrypt --download bct_mb1 mb1_bct_MB1_sigheader.bct.encrypt
[   0.5602 ] BR_CID: 0x80012344705DF1172C0000000D020080
[   0.5841 ] Sending bct_br
[   0.5841 ] ERROR: might be timeout in USB write.
Error: Return value 3
Command tegrarcm_v2 --new_session --chip 0x23 0 --uid --download bct_br br_bct_BR.bct --download mb1 mb1_t234_prod_aligned_sigheader.bin.encrypt --download psc_bl1 psc_bl1_t234_prod_aligned_sigheader.bin.encrypt --download bct_mb1 mb1_bct_MB1_sigheader.bct.encrypt
[  10.6781 ] tegrarcm_v2 --chip 0x23 0 --ismb2applet
[  10.6786 ] tegrarcm_v2 --chip 0x23 0 --ismb2applet
[  10.6790 ] Retrieving board information
[  10.6791 ] tegrarcm_v2 --chip 0x23 0 --oem platformdetails chip chip_info.bin
[  10.6794 ] Retrieving EEPROM data
[  10.6794 ] tegrarcm_v2 --oem platformdetails eeprom cvm /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/cvm.bin --chip 0x23 0
[  10.6798 ] tegrarcm_v2 --chip 0x23 0 --ismb2applet
[  10.6802 ] tegrarcm_v2 --chip 0x23 0 --ismb2applet
[  10.6804 ] Dumping customer Info
[  10.6806 ] tegrarcm_v2 --chip 0x23 0 --oem dump bct tmp.bct
[  10.6809 ] tegrabct_v2 --brbct tmp.bct --chip 0x23 0 --custinfo /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/custinfo_out.bin
[  10.6810 ] File tmp.bct open failed
[  10.6812 ] Error: try getting custinfo fail. Moving on
[  10.6812 ] Rebooting to recovery mode
[  10.6816 ] tegrarcm_v2 --chip 0x23 0 --ismb2
[  10.6820 ] Rebooting to recovery mode
[  10.6822 ] tegrarcm_v2 --chip 0x23 0 --reboot recovery
Board ID(3701) version(500) sku(0004) revision(F.0)
Chip SKU(00:00:00:D2) ramcode(00:00:00:00) fuselevel(fuselevel_production) board_FAB(500)
Copy /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/tegra234-p3737-0000+p3701-0004-nv.dtb to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/tegra234-p3737-0000+p3701-0004-nv.dtb.rec
copying bctfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-p3701-0000-sdram-l4t.dts)... done.
copying minratchet_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-ratchet-p3701-0000.dts)... done.
copying device_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-device-p3701-0000.dts)... done.
copying misc_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-misc-p3701-0000.dts)... done.
copying pinmux_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-pinmux-p3701-0000-a04.dtsi)... done.
copying gpioint_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-gpioint-p3701-0000.dts)... done.
copying pmic_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-pmic-p3701-0005.dts)... done.
copying pmc_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-padvoltage-p3701-0000-a04.dtsi)... done.
copying deviceprod_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-cprod-p3701-0000.dts)... done.
copying prod_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-prod-p3701-0000.dts)... done.
copying scr_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb2-bct-scr-p3701-0000.dts)... done.
copying wb0sdram(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-p3701-0000-wb0sdram-l4t.dts)... done.
copying bootrom_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-reset-p3701-0000.dts)... done.
Existing uphylane_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/tegra234-mb1-bct-uphylane-si.dtsi) reused.
copying dev_params(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-br-bct-p3701-0000.dts)... done.
copying dev_params_b(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-br-bct_b-p3701-0000.dts)... done.
copying mb2bct_cfg(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb2-bct-misc-p3701-0000.dts)... done.
Existing pscfwfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/pscfw_t234_prod.bin) reused.
Existing pscbl1file(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/psc_bl1_t234_prod.bin) reused.
Existing mtsmcefile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/mce_flash_o10_cr_prod.bin) reused.
Existing tscfwfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/tsec_t234.bin) reused.
Existing mb2applet(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/applet_t234.bin) reused.
Existing bootloader(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/mb2_t234.bin) reused.
copying initrd(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/l4t_initrd.img)... done.
bl is uefi
Making Boot image... done.
Not signing of boot.img
Making recovery ramdisk for recovery image...
Re-generating recovery ramdisk for recovery image...
/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/ramdisk_tmp /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra
54794 blocks

gzip: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/Image: not in gzip format
_BASE_KERNEL_VERSION=5.15.136-tegra
cp: cannot stat '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/rootfs/usr/bin/busybox': No such file or directory
warning: cp -f /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/rootfs/usr/bin/busybox /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/ramdisk_tmp//bin/busybox
76390 blocks
Making Recovery image...
copying recdtbfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/tegra234-p3737-0000+p3701-0004-nv.dtb.rec)... done.
20+0 records in
20+0 records out
20 bytes copied, 0.000135568 s, 148 kB/s
Existing sosfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/mb1_t234_prod.bin) reused.
Existing tegraboot(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/mb2_t234.bin) reused.
Existing cpu_bootloader(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/mb2_t234.bin) reused.
Existing mb2blfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/mb2_t234.bin) reused.
Existing xusbfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/xusb_t234_prod.bin) reused.
Existing pvafile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/nvpva_020.fw) reused.
Existing dcefile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/display-t234-dce.bin) reused.
Existing nvdecfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/nvdec_t234_prod.fw) reused.
Existing psc_rf(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/psc_rf_t234_prod.bin) reused.
Existing mb2_rf(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/mb2rf_t234.bin) reused.
Existing mb1file(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/mb1_t234_prod.bin) reused.
Existing bpffile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/bpmp_t234-TE990M-A1_prod.bin) reused.
copying bpfdtbfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/tegra234-bpmp-3701-0004-3737-0000.dtb)... done.
Existing camerafw(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/camera-rtcpu-t234-rce.img) reused.
Existing apefile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/adsp-fw.bin) reused.
Existing spefile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/spe_t234.bin) reused.
Existing wb0boot(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/sc7_t234_prod.bin) reused.
Existing tosfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/tos-optee_t234.img) reused.
Existing eksfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/eks_t234.img) reused.
copying dtbfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/tegra234-p3737-0000+p3701-0004-nv.dtb)... done.
Copying nv_boot_control.conf to rootfs
Skip generating system.img
Not signing of kernel-dtb
Existing tbcfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/uefi_jetson.bin) reused.
131072+0 records in
131072+0 records out
67108864 bytes (67 MB, 64 MiB) copied, 0.352293 s, 190 MB/s
	Sync'ing esp.img ... done.
copying tbcdtbfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/tegra234-p3737-0000+p3701-0004-nv.dtb)... done.
copying cfgfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/cfg/flash_t234_qspi.xml) to flash.xml... done.
Existing flashapp(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/tegraflash.py) reused.
copying overlay_dtb(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/L4TConfiguration.dtbo)... done.
copying overlay_dtb(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/tegra234-carveouts.dtbo)... done.
copying overlay_dtb(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/tegra-optee.dtbo)... done.
copying overlay_dtb(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/tegra234-p3737-camera-dual-imx274-overlay.dtbo)... done.
copying overlay_dtb(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/tegra234-p3737-camera-e3331-overlay.dtbo)... done.
copying overlay_dtb(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/tegra234-p3737-camera-e3333-overlay.dtbo)... done.
copying overlay_dtb(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/tegra234-p3737-camera-imx185-overlay.dtbo)... done.
copying overlay_dtb(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/BootOrderNvme.dtbo)... done.
/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/L4TConfiguration_updated.dts: Warning (unit_address_vs_reg): Node /fragment@0 has a unit name, but no reg property
/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/L4TConfiguration.dtbo: Warning (unit_address_vs_reg): Node /fragment@0 has a unit name, but no reg property
./tegraflash.py --bl uefi_jetson_with_dtb.bin --odmdata gbe-uphy-config-22,nvhs-uphy-config-0,hsio-uphy-config-0,gbe0-enable-10g,hsstp-lane-map-3 --overlay_dtb L4TConfiguration.dtbo,tegra234-carveouts.dtbo,tegra-optee.dtbo,tegra234-p3737-camera-dual-imx274-overlay.dtbo,tegra234-p3737-camera-e3331-overlay.dtbo,tegra234-p3737-camera-e3333-overlay.dtbo,tegra234-p3737-camera-imx185-overlay.dtbo,BootOrderNvme.dtbo, --bldtb tegra234-p3737-0000+p3701-0004-nv.dtb --applet mb1_t234_prod.bin --cmd "sign" --cfg flash.xml --chip "0x23" --concat_cpubl_bldtb --cpubl uefi_jetson.bin --minratchet_config tegra234-mb1-bct-ratchet-p3701-0000.dts --device_config tegra234-mb1-bct-device-p3701-0000.dts --misc_config tegra234-mb1-bct-misc-p3701-0000.dts --pinmux_config tegra234-mb1-bct-pinmux-p3701-0000-a04.dtsi --gpioint_config tegra234-mb1-bct-gpioint-p3701-0000.dts --pmic_config tegra234-mb1-bct-pmic-p3701-0005.dts --pmc_config tegra234-mb1-bct-padvoltage-p3701-0000-a04.dtsi --deviceprod_config tegra234-mb1-bct-cprod-p3701-0000.dts --prod_config tegra234-mb1-bct-prod-p3701-0000.dts --scr_config tegra234-mb2-bct-scr-p3701-0000.dts --wb0sdram_config tegra234-p3701-0000-wb0sdram-l4t.dts --br_cmd_config tegra234-mb1-bct-reset-p3701-0000.dts --uphy tegra234-mb1-bct-uphylane-si.dtsi --dev_params tegra234-br-bct-p3701-0000.dts,tegra234-br-bct_b-p3701-0000.dts --mb2bct_cfg tegra234-mb2-bct-misc-p3701-0000.dts --bins "psc_fw pscfw_t234_prod.bin; mts_mce mce_flash_o10_cr_prod.bin; tsec_fw tsec_t234.bin; mb2_applet applet_t234.bin; mb2_bootloader mb2_t234.bin; xusb_fw xusb_t234_prod.bin; pva_fw nvpva_020.fw; dce_fw display-t234-dce.bin; nvdec nvdec_t234_prod.fw; bpmp_fw bpmp_t234-TE990M-A1_prod.bin; bpmp_fw_dtb tegra234-bpmp-3701-0004-3737-0000.dtb; rce_fw camera-rtcpu-t234-rce.img; ape_fw adsp-fw.bin; spe_fw spe_t234.bin; tos tos-optee_t234.img; eks eks_t234.img" --sdram_config tegra234-p3701-0000-sdram-l4t.dts --cust_info custinfo_out.bin --bct_backup --boot_chain A 
Welcome to Tegra Flash
version 1.0.0
Type ? or help for help and q or quit to exit
Use ! to execute system commands
 
[   0.0106 ] tegrasign_v3.py --key None --getmode mode.txt
[   0.0106 ] Assuming zero filled SBK key
[   0.0103 ] Parsing partition layout
[   0.0105 ] tegraparser_v2 --pt flash.xml.tmp
[   0.0130 ] Change tegra234-bpmp-3701-0004-3737-0000.dtb to tegra234-bpmp-3701-0004-3737-0000_with_odm.dtb
[   0.0130 ] Change tegra234-bpmp-3701-0004-3737-0000.dtb to tegra234-bpmp-3701-0004-3737-0000_with_odm.dtb
[   0.0543 ] /usr/bin/python3 dtbcheck.py -c t234 -o tegra234-bpmp-3701-0004-3737-0000_with_odm.dtb tegra234-bpmp-3701-0004-3737-0000_with_odm_tmp.dtb
[   0.9684 ] Concatenating L4TConfiguration.dtbo,tegra234-carveouts.dtbo,tegra-optee.dtbo,tegra234-p3737-camera-dual-imx274-overlay.dtbo,tegra234-p3737-camera-e3331-overlay.dtbo,tegra234-p3737-camera-e3333-overlay.dtbo,tegra234-p3737-camera-imx185-overlay.dtbo,BootOrderNvme.dtbo to tegra234-p3737-0000+p3701-0004-nv_with_odm_overlay.dtb.updated
[   0.9685 ] Concatenating bl dtb to cpubl binary
[   0.9700 ] MB2 binary: mb2_t234.bin
[   0.9701 ] Pre-processing mb2bct config: tegra234-mb2-bct-misc-p3701-0000.dts
[   1.0795 ] Pre-processing mb2bct config: tegra234-mb2-bct-scr-p3701-0000.dts
[   1.6324 ] Generating coldboot mb2-bct
[   1.6324 ] tegrabct_v2 --chip 0x23 0 --mb2bct mb2_cold_boot_bct.cfg --mb2bctcfg tegra234-mb2-bct-misc-p3701-0000_cpp.dtb --scr tegra234-mb2-bct-scr-p3701-0000_cpp.dtb
[   1.6326 ] ERROR: value 0x31 is out of range
[   1.6336 ] ERROR: value 0x31 is out of range
[   1.6336 ] ERROR: value 0x31 is out of range
[   1.6337 ] ERROR: value 0x31 is out of range
[   1.6337 ] WARNING: unknown property 'tfc_version'
[   1.6340 ] WARNING: unknown property 'addr_header_version'
[   1.6448 ] Updating mb2-bct with storage information
[   1.6452 ] tegrabct_v2 --chip 0x23 0 --mb2bct mb2_cold_boot_bct_MB2.bct --updatestorageinfo flash.xml.bin
[   1.7811 ] Concatenating mb2-bct to mb2 binary
[   1.7811 ] mb2_bin_file = mb2_t234.bin
[   1.7811 ] mb2_bct_file = mb2_cold_boot_bct_MB2.bct
[   1.7835 ] DCE binary: display-t234-dce.bin
[   1.7836 ] Kernel DTB used: tegra234-p3737-0000+p3701-0004-nv_with_odm_overlay.dtb.updated
[   1.7836 ] Concatenating kernel-dtb to dce-fw binary
[   1.7836 ] dce_bin = display-t234-dce.bin
[   1.7836 ] kernel_dtb = tegra234-p3737-0000+p3701-0004-nv_with_odm_overlay.dtb.updated
[   1.7836 ] dce_with_dtb = display-t234-dce_with_tegra234-p3737-0000+p3701-0004-nv_with_odm_overlay.dtb.bin
[   1.7893 ] Update display-t234-dce_with_tegra234-p3737-0000+p3701-0004-nv_with_odm_overlay.dtb.bin to dce_fw partitions
[   1.7909 ] Parsing partition layout
[   1.7913 ] tegraparser_v2 --pt flash.xml.tmp
[   1.7921 ] Creating list of images to be signed
[   1.7924 ] Generating ratchet blob
[   1.7925 ] Pre-processing config: tegra234-mb1-bct-reset-p3701-0000.dts
[   1.7976 ] Pre-processing config: tegra234-mb1-bct-device-p3701-0000.dts
[   1.8024 ] Pre-processing config: tegra234-mb1-bct-cprod-p3701-0000.dts
[   1.8067 ] Pre-processing config: tegra234-mb1-bct-gpioint-p3701-0000.dts
[   1.8110 ] Pre-processing config: tegra234-mb1-bct-misc-p3701-0000.dts
[   1.8184 ] Pre-processing config: tegra234-mb1-bct-pinmux-p3701-0000-a04.dtsi
[   1.8296 ] Pre-processing config: tegra234-mb1-bct-padvoltage-p3701-0000-a04.dtsi
[   1.8340 ] Pre-processing config: tegra234-mb1-bct-pmic-p3701-0005.dts
[   1.8398 ] Pre-processing config: tegra234-mb1-bct-prod-p3701-0000.dts
[   1.8448 ] Pre-processing config: tegra234-p3701-0000-sdram-l4t.dts
[   3.1451 ] Pre-processing config: tegra234-mb1-bct-uphylane-si.dtsi
[   3.1505 ] Pre-processing config: tegra234-p3701-0000-wb0sdram-l4t.dts
[   4.2030 ] Pre-processing config: tegra234-mb1-bct-ratchet-p3701-0000.dts
[   4.2084 ] Generating coldboot mb1-bct
[   4.2086 ] tegrabct_v2 --chip 0x23 0 --mb1bct mb1_cold_boot_bct.cfg --misc tegra234-mb1-bct-misc-p3701-0000_cpp.dtb --wb0sdram tegra234-p3701-0000-wb0sdram-l4t_cpp.dtb --pinmux tegra234-mb1-bct-pinmux-p3701-0000-a04_cpp.dtb --pmc tegra234-mb1-bct-padvoltage-p3701-0000-a04_cpp.dtb --pmic tegra234-mb1-bct-pmic-p3701-0005_cpp.dtb --brcommand tegra234-mb1-bct-reset-p3701-0000_cpp.dtb --prod tegra234-mb1-bct-prod-p3701-0000_cpp.dtb --gpioint tegra234-mb1-bct-gpioint-p3701-0000_cpp.dtb --uphy tegra234-mb1-bct-uphylane-si_cpp.dtb --device tegra234-mb1-bct-device-p3701-0000_cpp.dtb --deviceprod tegra234-mb1-bct-cprod-p3701-0000_cpp.dtb --minratchet tegra234-mb1-bct-ratchet-p3701-0000_cpp.dtb --ratchet_blob ratchet_blob.bin
[   4.2087 ] MB1-BCT version: 0.13

[   4.2101 ] Parsing config file :tegra234-mb1-bct-pinmux-p3701-0000-a04_cpp.dtb 
[   4.2103 ] Added Platform Config 0 data with size :- 3320

[   4.2122 ] Parsing config file :tegra234-mb1-bct-padvoltage-p3701-0000-a04_cpp.dtb 
[   4.2124 ] WARNING: unknown node 'g2'
[   4.2125 ] WARNING: unknown node 'g2'
[   4.2126 ] WARNING: unknown node 'g9'
[   4.2128 ] WARNING: unknown node 'g9'
[   4.2128 ] Added Platform Config 2 data with size :- 24
[   4.2128 ] 
[   4.2128 ] Parsing config file :tegra234-mb1-bct-pmic-p3701-0005_cpp.dtb 
[   4.2128 ] Added Platform Config 4 data with size :- 580
[   4.2128 ] 
[   4.2128 ] Parsing config file :tegra234-mb1-bct-reset-p3701-0000_cpp.dtb 
[   4.2128 ] Added Platform Config 3 data with size :- 52
[   4.2128 ] 
[   4.2128 ] Parsing config file :tegra234-mb1-bct-prod-p3701-0000_cpp.dtb 
[   4.2128 ] WARNING: unknown property 'major'
[   4.2128 ] WARNING: unknown property 'minor'
[   4.2128 ] Added Platform Config 5 data with size :- 524
[   4.2128 ] 
[   4.2128 ] Parsing config file :tegra234-mb1-bct-gpioint-p3701-0000_cpp.dtb 
[   4.2128 ] WARNING: unknown property 'major'
[   4.2128 ] WARNING: unknown property 'minor'
[   4.2128 ] Added Platform Config 7 data with size :- 380
[   4.2128 ] 
[   4.2128 ] Parsing config file :tegra234-mb1-bct-uphylane-si_cpp.dtb 
[   4.2128 ] Added Platform Config 8 data with size :- 24
[   4.2128 ] 
[   4.2128 ] Parsing config file :tegra234-mb1-bct-device-p3701-0000_cpp.dtb 
[   4.2128 ] Added Platform Config 9 data with size :- 100
[   4.2128 ] 
[   4.2128 ] Parsing config file :tegra234-mb1-bct-cprod-p3701-0000_cpp.dtb 
[   4.2128 ] ModuleCount 0 NumProdNames 0
[   4.2128 ] Added Platform Config 6 data with size :- 16
[   4.2128 ] 
[   4.2128 ] Parsing config file :tegra234-mb1-bct-ratchet-p3701-0000_cpp.dtb 
[   4.2128 ] 
[   4.2128 ] Updating mb1-bct with firmware information
[   4.2131 ] tegrabct_v2 --chip 0x23 0 --mb1bct mb1_cold_boot_bct_MB1.bct --updatefwinfo flash.xml.bin
[   4.2146 ] tegrahost_v2 --chip 0x23 0 --align mb1_cold_boot_bct_MB1_aligned.bct
[   4.2149 ] Generating SHA2 Hash for mb1bct
[   4.2162 ] Sha saved in mb1_cold_boot_bct_MB1_aligned.sha
[   4.2169 ] Sha saved in mb1_cold_boot_bct_MB1.sha
[   4.2166 ] tegrahost_v2 --chip 0x23 0 --magicid MBCT --ratchet_blob ratchet_blob.bin --appendsigheader mb1_cold_boot_bct_MB1_aligned.bct zerosbk
[   4.2168 ] adding BCH for mb1_cold_boot_bct_MB1_aligned.bct
[   4.2179 ] tegrasign_v3.py --key None --list mb1_cold_boot_bct_MB1_aligned_sigheader.bct_list.xml --pubkeyhash pub_key.key --sha sha512
[   4.2181 ] Assuming zero filled SBK key
[   4.2189 ] Warning: pub_key.key is not found
[   4.2187 ] tegrahost_v2 --chip 0x23 0 --updatesigheader mb1_cold_boot_bct_MB1_aligned_sigheader.bct.encrypt mb1_cold_boot_bct_MB1_aligned_sigheader.bct.hash zerosbk
[   4.2192 ] tegrahost_v2 --chip 0x23 0 --partitionlayout flash.xml.bin --ratchet_blob ratchet_blob.bin --list images_list.xml zerosbk
[   4.2193 ] MB1: Nvheader already present is mb1_t234_prod_aligned.bin
[   4.2202 ] Header already present for mb1_t234_prod_aligned_sigheader.bin
[   4.2203 ] MB1: Nvheader already present is psc_bl1_t234_prod_aligned.bin
[   4.2226 ] Header already present for psc_bl1_t234_prod_aligned_sigheader.bin
[   4.2227 ] Header already present for tsec_t234_aligned.bin
[   4.2237 ] Header already present for nvdec_t234_prod_aligned.fw
[   4.2253 ] adding BCH for mb2_t234_with_mb2_cold_boot_bct_MB2_aligned.bin
[   4.2281 ] adding BCH for xusb_t234_prod_aligned.bin
[   4.2347 ] Header already present for bpmp_t234-TE990M-A1_prod_aligned.bin
[   4.2384 ] adding BCH for tegra234-bpmp-3701-0004-3737-0000_with_odm_aligned.dtb
[   4.2464 ] Header already present for pscfw_t234_prod_aligned.bin
[   4.2521 ] Header already present for mce_flash_o10_cr_prod_aligned.bin
[   4.2544 ] Header already present for sc7_t234_prod.bin
[   4.2558 ] Header already present for psc_rf_t234_prod_aligned.bin
[   4.2572 ] adding BCH for mb2rf_t234_aligned.bin
[   4.2581 ] INFO: compressing uefi_jetson_with_dtb_aligned.bin
[   4.2891 ] INFO: complete compression, uefi_jetson_with_dtb_aligned.bin, ratio = 89%
[   4.2929 ] adding BCH for uefi_jetson_with_dtb_aligned_blob_w_bin_aligned.bin
[   4.3202 ] adding BCH for tos-optee_t234_aligned.img
[   4.3465 ] adding BCH for eks_t234_aligned.img
[   4.3694 ] INFO: compressing display-t234-dce_with_tegra234-p3737-0000+p3701-0004-nv_with_odm_overlay.dtb_aligned.bin
[   4.4683 ] INFO: complete compression, display-t234-dce_with_tegra234-p3737-0000+p3701-0004-nv_with_odm_overlay.dtb_aligned.bin, ratio = 6%
[   4.4802 ] adding BCH for display-t234-dce_with_tegra234-p3737-0000+p3701-0004-nv_with_odm_overlay.dtb_aligned_blob_w_bin_aligned.bin
[   4.4915 ] adding BCH for spe_t234_aligned.bin
[   4.4982 ] adding BCH for camera-rtcpu-t234-rce_aligned.img
[   4.5025 ] adding BCH for adsp-fw_aligned.bin
[   4.5094 ] INFO: compressing nvpva_020_aligned.fw
[   4.5323 ] INFO: complete compression, nvpva_020_aligned.fw, ratio = 2%
[   4.5336 ] adding BCH for nvpva_020_aligned_blob_w_bin_aligned.fw
[   4.5347 ] MB1: Nvheader already present is mb1_t234_prod_aligned.bin
[   4.5355 ] Header already present for mb1_t234_prod_aligned_sigheader.bin
[   4.5356 ] MB1: Nvheader already present is psc_bl1_t234_prod_aligned.bin
[   4.5378 ] Header already present for psc_bl1_t234_prod_aligned_sigheader.bin
[   4.5379 ] Header already present for tsec_t234_aligned.bin
[   4.5397 ] Header already present for nvdec_t234_prod_aligned.fw
[   4.5412 ] adding BCH for mb2_t234_with_mb2_cold_boot_bct_MB2_aligned.bin
[   4.5439 ] adding BCH for xusb_t234_prod_aligned.bin
[   4.5503 ] Header already present for bpmp_t234-TE990M-A1_prod_aligned.bin
[   4.5540 ] adding BCH for tegra234-bpmp-3701-0004-3737-0000_with_odm_aligned.dtb
[   4.5620 ] Header already present for pscfw_t234_prod_aligned.bin
[   4.5676 ] Header already present for mce_flash_o10_cr_prod_aligned.bin
[   4.5700 ] Header already present for sc7_t234_prod.bin
[   4.5713 ] Header already present for psc_rf_t234_prod_aligned.bin
[   4.5728 ] adding BCH for mb2rf_t234_aligned.bin
[   4.5737 ] INFO: compressing uefi_jetson_with_dtb_aligned.bin
[   4.6052 ] INFO: complete compression, uefi_jetson_with_dtb_aligned.bin, ratio = 89%
[   4.6088 ] adding BCH for uefi_jetson_with_dtb_aligned_blob_w_bin_aligned.bin
[   4.6374 ] adding BCH for tos-optee_t234_aligned.img
[   4.6655 ] adding BCH for eks_t234_aligned.img
[   4.6889 ] INFO: compressing display-t234-dce_with_tegra234-p3737-0000+p3701-0004-nv_with_odm_overlay.dtb_aligned.bin
[   4.7886 ] INFO: complete compression, display-t234-dce_with_tegra234-p3737-0000+p3701-0004-nv_with_odm_overlay.dtb_aligned.bin, ratio = 6%
[   4.7986 ] adding BCH for display-t234-dce_with_tegra234-p3737-0000+p3701-0004-nv_with_odm_overlay.dtb_aligned_blob_w_bin_aligned.bin
[   4.8088 ] adding BCH for spe_t234_aligned.bin
[   4.8148 ] adding BCH for camera-rtcpu-t234-rce_aligned.img
[   4.8188 ] adding BCH for adsp-fw_aligned.bin
[   4.8259 ] INFO: compressing nvpva_020_aligned.fw
[   4.8495 ] INFO: complete compression, nvpva_020_aligned.fw, ratio = 2%
[   4.8508 ] adding BCH for nvpva_020_aligned_blob_w_bin_aligned.fw
[   4.8526 ] Filling MB1 storage info
[   4.8526 ] Parsing dev params for multi chains
[   4.8584 ] Generating br-bct
[   4.8586 ] Updating dev and MSS params in BR BCT
[   4.8586 ] tegrabct_v2 --dev_param tegra234-br-bct-p3701-0000_cpp.dtb --sdram tegra234-p3701-0000-sdram-l4t_cpp.dtb --brbct br_bct.cfg --chip 0x23 0
[   4.9263 ] Updating bl info
[   4.9267 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updateblinfo flash.xml.bin
[   4.9323 ] Generating br-bct
[   4.9324 ] Updating dev and MSS params in BR BCT
[   4.9324 ] tegrabct_v2 --dev_param tegra234-br-bct_b-p3701-0000_cpp.dtb --sdram tegra234-p3701-0000-sdram-l4t_cpp.dtb --brbct br_bct.cfg --chip 0x23 0
[   4.9939 ] Updating bl info
[   4.9943 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updateblinfo flash.xml.bin
[   4.9951 ] Generating BCT backup image
[   4.9951 ] dd if=/dev/zero of=bct_backup.img bs=1 count=32768
[   4.9953 ] 32768+0 records in
[   5.0101 ] 32768+0 records out
[   5.0101 ] 32768 bytes (33 kB, 32 KiB) copied, 0.0141697 s, 2.3 MB/s
[   5.0101 ] 
[   5.0101 ] Concatenating BCT for chain A to bct_backup.img

[   5.0101 ] dd if=br_bct_BR.bct of=bct_backup.img bs=1 seek=0 conv=notrunc
[   5.0104 ] 8192+0 records in
[   5.0166 ] 8192+0 records out
[   5.0166 ] 8192 bytes (8.2 kB, 8.0 KiB) copied, 0.00568908 s, 1.4 MB/s
[   5.0166 ] 
[   5.0166 ] Concatenating BCT for chain B to bct_backup.img

[   5.0166 ] dd if=br_bct_b_BR.bct of=bct_backup.img bs=1 seek=16384 conv=notrunc
[   5.0168 ] 8192+0 records in
[   5.0239 ] 8192+0 records out
[   5.0240 ] 8192 bytes (8.2 kB, 8.0 KiB) copied, 0.006712 s, 1.2 MB/s
[   5.0240 ] 
[   5.0240 ] Generating signatures
[   5.0244 ] tegrasign_v3.py --key None --list images_list.xml --pubkeyhash pub_key.key --sha sha512
[   5.0246 ] Assuming zero filled SBK key
[   5.0782 ] Warning: pub_key.key is not found
[   5.0790 ] Parsing dev params for multi chains
[   5.0791 ] Generating br-bct
[   5.0793 ] Updating dev and MSS params in BR BCT
[   5.0793 ] tegrabct_v2 --dev_param tegra234-br-bct-p3701-0000_cpp.dtb --sdram tegra234-p3701-0000-sdram-l4t_cpp.dtb --brbct br_bct.cfg --chip 0x23 0
[   5.1411 ] Updating customer data section
[   5.1413 ] tegrabct_v2 --chip 0x23 0 --brbct br_bct_BR.bct --update_custinfo custinfo_out.bin
[   5.1424 ] Updating bl info
[   5.1425 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updateblinfo flash.xml.bin --updatesig images_list_signed.xml
[   5.1440 ] Generating SHA2 Hash
[   5.1449 ] Sha saved in br_bct_BR.sha
[   5.1445 ] Get Signed section of bct
[   5.1447 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --listbct bct_list.xml
[   5.1451 ] Signing BCT
[   5.1455 ] tegrasign_v3.py --key None --list bct_list.xml --pubkeyhash pub_key.key --sha sha512
[   5.1456 ] Assuming zero filled SBK key
[   5.1466 ] Sha saved in br_bct_BR.sha
[   5.1467 ] Warning: pub_key.key is not found
[   5.1463 ] Updating BCT with signature
[   5.1464 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updatesig bct_list_signed.xml
[   5.1466 ] Offset :4608 Len :3584
[   5.1471 ] Generating SHA2 Hash
[   5.1476 ] tegrasign_v3.py --key None --list bct_list.xml --sha sha512
[   5.1477 ] Assuming zero filled SBK key
[   5.1477 ] Assuming zero filled SBK key
[   5.1490 ] Sha saved in br_bct_BR.sha
[   5.1486 ] Updating BCT with SHA2 Hash
[   5.1488 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updatesha bct_list_signed.xml
[   5.1490 ] Offset :4608 Len :3584
[   5.1493 ] Offset :68 Len :8124
[   5.1496 ] Generating br-bct
[   5.1499 ] Updating dev and MSS params in BR BCT
[   5.1500 ] tegrabct_v2 --dev_param tegra234-br-bct_b-p3701-0000_cpp.dtb --sdram tegra234-p3701-0000-sdram-l4t_cpp.dtb --brbct br_bct.cfg --chip 0x23 0
[   5.2169 ] Updating customer data section
[   5.2173 ] tegrabct_v2 --chip 0x23 0 --brbct br_bct_BR.bct --update_custinfo custinfo_out.bin
[   5.2183 ] Updating bl info
[   5.2185 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updateblinfo flash.xml.bin --updatesig images_list_signed.xml
[   5.2201 ] Generating SHA2 Hash
[   5.2212 ] Sha saved in br_bct_BR.sha
[   5.2208 ] Get Signed section of bct
[   5.2210 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --listbct bct_list.xml
[   5.2213 ] Signing BCT
[   5.2218 ] tegrasign_v3.py --key None --list bct_list.xml --pubkeyhash pub_key.key --sha sha512
[   5.2219 ] Assuming zero filled SBK key
[   5.2230 ] Sha saved in br_bct_BR.sha
[   5.2232 ] Warning: pub_key.key is not found
[   5.2227 ] Updating BCT with signature
[   5.2230 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updatesig bct_list_signed.xml
[   5.2232 ] Offset :4608 Len :3584
[   5.2237 ] Generating SHA2 Hash
[   5.2242 ] tegrasign_v3.py --key None --list bct_list.xml --sha sha512
[   5.2243 ] Assuming zero filled SBK key
[   5.2243 ] Assuming zero filled SBK key
[   5.2259 ] Sha saved in br_bct_BR.sha
[   5.2255 ] Updating BCT with SHA2 Hash
[   5.2257 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updatesha bct_list_signed.xml
[   5.2259 ] Offset :4608 Len :3584
[   5.2261 ] Offset :68 Len :8124
[   5.2265 ] Generating BCT backup image
[   5.2265 ] dd if=/dev/zero of=bct_backup.img bs=1 count=32768
[   5.2268 ] 32768+0 records in
[   5.2456 ] 32768+0 records out
[   5.2456 ] 32768 bytes (33 kB, 32 KiB) copied, 0.0182501 s, 1.8 MB/s
[   5.2456 ] 
[   5.2456 ] Concatenating BCT for chain A to bct_backup.img

[   5.2456 ] dd if=br_bct_BR.bct of=bct_backup.img bs=1 seek=0 conv=notrunc
[   5.2459 ] 8192+0 records in
[   5.2509 ] 8192+0 records out
[   5.2509 ] 8192 bytes (8.2 kB, 8.0 KiB) copied, 0.00456048 s, 1.8 MB/s
[   5.2509 ] 
[   5.2509 ] Concatenating BCT for chain B to bct_backup.img

[   5.2509 ] dd if=br_bct_b_BR.bct of=bct_backup.img bs=1 seek=16384 conv=notrunc
[   5.2512 ] 8192+0 records in
[   5.2578 ] 8192+0 records out
[   5.2579 ] 8192 bytes (8.2 kB, 8.0 KiB) copied, 0.00629522 s, 1.3 MB/s
[   5.2579 ] 
[   5.2579 ] Generating coldboot mb1-bct
[   5.2581 ] tegrabct_v2 --chip 0x23 0 --mb1bct mb1_cold_boot_bct.cfg --misc tegra234-mb1-bct-misc-p3701-0000_cpp.dtb --wb0sdram tegra234-p3701-0000-wb0sdram-l4t_cpp.dtb --pinmux tegra234-mb1-bct-pinmux-p3701-0000-a04_cpp.dtb --pmc tegra234-mb1-bct-padvoltage-p3701-0000-a04_cpp.dtb --pmic tegra234-mb1-bct-pmic-p3701-0005_cpp.dtb --brcommand tegra234-mb1-bct-reset-p3701-0000_cpp.dtb --prod tegra234-mb1-bct-prod-p3701-0000_cpp.dtb --gpioint tegra234-mb1-bct-gpioint-p3701-0000_cpp.dtb --uphy tegra234-mb1-bct-uphylane-si_cpp.dtb --device tegra234-mb1-bct-device-p3701-0000_cpp.dtb --deviceprod tegra234-mb1-bct-cprod-p3701-0000_cpp.dtb --minratchet tegra234-mb1-bct-ratchet-p3701-0000_cpp.dtb --ratchet_blob ratchet_blob.bin
[   5.2583 ] MB1-BCT version: 0.13

[   5.2597 ] Parsing config file :tegra234-mb1-bct-pinmux-p3701-0000-a04_cpp.dtb 
[   5.2599 ] Added Platform Config 0 data with size :- 3320

[   5.2624 ] Parsing config file :tegra234-mb1-bct-padvoltage-p3701-0000-a04_cpp.dtb 
[   5.2625 ] WARNING: unknown node 'g2'
[   5.2626 ] WARNING: unknown node 'g2'
[   5.2626 ] WARNING: unknown node 'g9'
[   5.2626 ] WARNING: unknown node 'g9'
[   5.2626 ] Added Platform Config 2 data with size :- 24

[   5.2627 ] Parsing config file :tegra234-mb1-bct-pmic-p3701-0005_cpp.dtb 
[   5.2628 ] Added Platform Config 4 data with size :- 580

[   5.2628 ] Parsing config file :tegra234-mb1-bct-reset-p3701-0000_cpp.dtb 
[   5.2629 ] Added Platform Config 3 data with size :- 52

[   5.2630 ] Parsing config file :tegra234-mb1-bct-prod-p3701-0000_cpp.dtb 
[   5.2630 ] WARNING: unknown property 'major'
[   5.2630 ] WARNING: unknown property 'minor'
[   5.2630 ] Added Platform Config 5 data with size :- 524
[   5.2630 ] 
[   5.2630 ] Parsing config file :tegra234-mb1-bct-gpioint-p3701-0000_cpp.dtb 
[   5.2630 ] WARNING: unknown property 'major'
[   5.2630 ] WARNING: unknown property 'minor'
[   5.2630 ] Added Platform Config 7 data with size :- 380
[   5.2630 ] 
[   5.2630 ] Parsing config file :tegra234-mb1-bct-uphylane-si_cpp.dtb 
[   5.2630 ] Added Platform Config 8 data with size :- 24
[   5.2630 ] 
[   5.2630 ] Parsing config file :tegra234-mb1-bct-device-p3701-0000_cpp.dtb 
[   5.2630 ] Added Platform Config 9 data with size :- 100
[   5.2630 ] 
[   5.2630 ] Parsing config file :tegra234-mb1-bct-cprod-p3701-0000_cpp.dtb 
[   5.2630 ] ModuleCount 0 NumProdNames 0
[   5.2630 ] Added Platform Config 6 data with size :- 16
[   5.2630 ] 
[   5.2630 ] Parsing config file :tegra234-mb1-bct-ratchet-p3701-0000_cpp.dtb 
[   5.2630 ] 
[   5.2630 ] Updating mb1-bct with firmware information
[   5.2632 ] tegrabct_v2 --chip 0x23 0 --mb1bct mb1_cold_boot_bct_MB1.bct --updatefwinfo flash.xml.bin
[   5.2644 ] tegrahost_v2 --chip 0x23 0 --align mb1_cold_boot_bct_MB1_aligned.bct
[   5.2647 ] Generating SHA2 Hash for mb1bct
[   5.2658 ] Sha saved in mb1_cold_boot_bct_MB1_aligned.sha
[   5.2664 ] Sha saved in mb1_cold_boot_bct_MB1.sha
[   5.2662 ] tegrahost_v2 --chip 0x23 0 --magicid MBCT --ratchet_blob ratchet_blob.bin --appendsigheader mb1_cold_boot_bct_MB1_aligned.bct zerosbk
[   5.2663 ] adding BCH for mb1_cold_boot_bct_MB1_aligned.bct
[   5.2676 ] tegrasign_v3.py --key None --list mb1_cold_boot_bct_MB1_aligned_sigheader.bct_list.xml --pubkeyhash pub_key.key --sha sha512
[   5.2677 ] Assuming zero filled SBK key
[   5.2688 ] Warning: pub_key.key is not found
[   5.2687 ] tegrahost_v2 --chip 0x23 0 --updatesigheader mb1_cold_boot_bct_MB1_aligned_sigheader.bct.encrypt mb1_cold_boot_bct_MB1_aligned_sigheader.bct.hash zerosbk
[   5.2694 ] Generating recovery mb1-bct
[   5.2696 ] tegrabct_v2 --chip 0x23 0 --mb1bct mb1_bct.cfg --misc tegra234-mb1-bct-misc-p3701-0000_cpp.dtb --wb0sdram tegra234-p3701-0000-wb0sdram-l4t_cpp.dtb --pinmux tegra234-mb1-bct-pinmux-p3701-0000-a04_cpp.dtb --pmc tegra234-mb1-bct-padvoltage-p3701-0000-a04_cpp.dtb --pmic tegra234-mb1-bct-pmic-p3701-0005_cpp.dtb --brcommand tegra234-mb1-bct-reset-p3701-0000_cpp.dtb --prod tegra234-mb1-bct-prod-p3701-0000_cpp.dtb --gpioint tegra234-mb1-bct-gpioint-p3701-0000_cpp.dtb --uphy tegra234-mb1-bct-uphylane-si_cpp.dtb --device tegra234-mb1-bct-device-p3701-0000_cpp.dtb --deviceprod tegra234-mb1-bct-cprod-p3701-0000_cpp.dtb --minratchet tegra234-mb1-bct-ratchet-p3701-0000_cpp.dtb --ratchet_blob ratchet_blob.bin
[   5.2699 ] MB1-BCT version: 0.13

[   5.2717 ] Parsing config file :tegra234-mb1-bct-pinmux-p3701-0000-a04_cpp.dtb 
[   5.2718 ] Added Platform Config 0 data with size :- 3320

[   5.2749 ] Parsing config file :tegra234-mb1-bct-padvoltage-p3701-0000-a04_cpp.dtb 
[   5.2750 ] WARNING: unknown node 'g2'
[   5.2751 ] WARNING: unknown node 'g2'
[   5.2751 ] WARNING: unknown node 'g9'
[   5.2751 ] WARNING: unknown node 'g9'
[   5.2752 ] Added Platform Config 2 data with size :- 24

[   5.2752 ] Parsing config file :tegra234-mb1-bct-pmic-p3701-0005_cpp.dtb 
[   5.2753 ] Added Platform Config 4 data with size :- 580

[   5.2753 ] Parsing config file :tegra234-mb1-bct-reset-p3701-0000_cpp.dtb 
[   5.2754 ] Added Platform Config 3 data with size :- 52

[   5.2755 ] Parsing config file :tegra234-mb1-bct-prod-p3701-0000_cpp.dtb 
[   5.2755 ] WARNING: unknown property 'major'
[   5.2756 ] WARNING: unknown property 'minor'
[   5.2756 ] Added Platform Config 5 data with size :- 524
[   5.2756 ] 
[   5.2756 ] Parsing config file :tegra234-mb1-bct-gpioint-p3701-0000_cpp.dtb 
[   5.2756 ] WARNING: unknown property 'major'
[   5.2756 ] WARNING: unknown property 'minor'
[   5.2756 ] Added Platform Config 7 data with size :- 380
[   5.2756 ] 
[   5.2756 ] Parsing config file :tegra234-mb1-bct-uphylane-si_cpp.dtb 
[   5.2756 ] Added Platform Config 8 data with size :- 24
[   5.2756 ] 
[   5.2756 ] Parsing config file :tegra234-mb1-bct-device-p3701-0000_cpp.dtb 
[   5.2756 ] Added Platform Config 9 data with size :- 100
[   5.2756 ] 
[   5.2756 ] Parsing config file :tegra234-mb1-bct-cprod-p3701-0000_cpp.dtb 
[   5.2756 ] ModuleCount 0 NumProdNames 0
[   5.2756 ] Added Platform Config 6 data with size :- 16
[   5.2756 ] 
[   5.2756 ] Parsing config file :tegra234-mb1-bct-ratchet-p3701-0000_cpp.dtb 
[   5.2756 ] 
[   5.2756 ] Updating mb1-bct with firmware information
[   5.2760 ] tegrabct_v2 --chip 0x23 0 --mb1bct mb1_bct_MB1.bct --recov --updatefwinfo flash.xml.bin
[   5.2770 ] tegrahost_v2 --chip 0x23 0 --align mb1_bct_MB1_aligned.bct
[   5.2773 ] Generating SHA2 Hash for mb1bct
[   5.2783 ] Sha saved in mb1_bct_MB1_aligned.sha
[   5.2789 ] Sha saved in mb1_bct_MB1.sha
[   5.2787 ] tegrahost_v2 --chip 0x23 0 --magicid MBCT --ratchet_blob ratchet_blob.bin --appendsigheader mb1_bct_MB1_aligned.bct zerosbk
[   5.2789 ] adding BCH for mb1_bct_MB1_aligned.bct
[   5.2800 ] tegrasign_v3.py --key None --list mb1_bct_MB1_aligned_sigheader.bct_list.xml --pubkeyhash pub_key.key --sha sha512
[   5.2801 ] Assuming zero filled SBK key
[   5.2811 ] Warning: pub_key.key is not found
[   5.2810 ] tegrahost_v2 --chip 0x23 0 --updatesigheader mb1_bct_MB1_aligned_sigheader.bct.encrypt mb1_bct_MB1_aligned_sigheader.bct.hash zerosbk
[   5.2816 ] Generating coldboot mem-bct
[   5.2818 ] tegrabct_v2 --chip 0x23 0 --sdram tegra234-p3701-0000-sdram-l4t_cpp.dtb --wb0sdram tegra234-p3701-0000-wb0sdram-l4t_cpp.dtb --membct tegra234-p3701-0000-sdram-l4t_cpp_1.bct tegra234-p3701-0000-sdram-l4t_cpp_2.bct tegra234-p3701-0000-sdram-l4t_cpp_3.bct tegra234-p3701-0000-sdram-l4t_cpp_4.bct
[   5.2820 ]  packing sdram params with Wb0 file tegra234-p3701-0000-wb0sdram-l4t_cpp.dtb
[   5.3458 ] Packing sdram param for instance[0]
[   5.3459 ] Packing sdram param for instance[1]
[   5.3459 ] Packing sdram param for instance[2]
[   5.3460 ] Packing sdram param for instance[3]
[   5.3460 ] Packing sdram param for instance[4]
[   5.3460 ] Packing sdram param for instance[5]
[   5.3461 ] Packing sdram param for instance[6]
[   5.3461 ] Packing sdram param for instance[7]
[   5.3462 ] Packing sdram param for instance[8]
[   5.3462 ] Packing sdram param for instance[9]
[   5.3463 ] Packing sdram param for instance[10]
[   5.3463 ] Packing sdram param for instance[11]
[   5.3464 ] Packing sdram param for instance[12]
[   5.3464 ] Packing sdram param for instance[13]
[   5.3465 ] Packing sdram param for instance[14]
[   5.3465 ] Packing sdram param for instance[15]
[   5.4074 ] Getting sector size from pt
[   5.4077 ] tegraparser_v2 --getsectorsize flash.xml.bin sector_info.bin
[   5.4081 ] BlockSize read from layout is 0x200

[   5.4083 ] tegrahost_v2 --chip 0x23 0 --blocksize 512 --magicid MEMB --addsigheader_multi tegra234-p3701-0000-sdram-l4t_cpp_1.bct tegra234-p3701-0000-sdram-l4t_cpp_2.bct tegra234-p3701-0000-sdram-l4t_cpp_3.bct tegra234-p3701-0000-sdram-l4t_cpp_4.bct
[   5.4085 ] Binary 0 length is 58752
[   5.4088 ] Binary 0 align length is 58880
[   5.4093 ] Binary 1 length is 58752
[   5.4093 ] Binary 1 align length is 58880
[   5.4097 ] Binary 2 length is 58752
[   5.4097 ] Binary 2 align length is 58880
[   5.4101 ] Binary 3 length is 58752
[   5.4101 ] Binary 3 align length is 58880
[   5.4105 ] Buffer length is 235520
[   5.4105 ] adding BCH for tegra234-p3701-0000-sdram-l4t_cpp_1.bct
[   5.4105 ] new length is 243712
[   5.4111 ] tegrahost_v2 --chip 0x23 0 --align mem_coldboot_aligned.bct
[   5.4115 ] tegrahost_v2 --chip 0x23 0 --magicid MEMB --ratchet_blob ratchet_blob.bin --appendsigheader mem_coldboot_aligned.bct zerosbk
[   5.4116 ] Header already present for mem_coldboot_aligned.bct
[   5.4129 ] tegrasign_v3.py --key None --list mem_coldboot_aligned_sigheader.bct_list.xml --pubkeyhash pub_key.key --sha sha512
[   5.4130 ] Assuming zero filled SBK key
[   5.4142 ] Warning: pub_key.key is not found
[   5.4141 ] tegrahost_v2 --chip 0x23 0 --updatesigheader mem_coldboot_aligned_sigheader.bct.encrypt mem_coldboot_aligned_sigheader.bct.hash zerosbk
[   5.4151 ] Generating recovery mem-bct
[   5.4154 ] tegrabct_v2 --chip 0x23 0 --sdram tegra234-p3701-0000-sdram-l4t_cpp.dtb --wb0sdram tegra234-p3701-0000-wb0sdram-l4t_cpp.dtb --membct tegra234-p3701-0000-sdram-l4t_cpp_1.bct tegra234-p3701-0000-sdram-l4t_cpp_2.bct tegra234-p3701-0000-sdram-l4t_cpp_3.bct tegra234-p3701-0000-sdram-l4t_cpp_4.bct
[   5.4156 ]  packing sdram params with Wb0 file tegra234-p3701-0000-wb0sdram-l4t_cpp.dtb
[   5.4771 ] Packing sdram param for instance[0]
[   5.4771 ] Packing sdram param for instance[1]
[   5.4772 ] Packing sdram param for instance[2]
[   5.4772 ] Packing sdram param for instance[3]
[   5.4772 ] Packing sdram param for instance[4]
[   5.4773 ] Packing sdram param for instance[5]
[   5.4773 ] Packing sdram param for instance[6]
[   5.4774 ] Packing sdram param for instance[7]
[   5.4774 ] Packing sdram param for instance[8]
[   5.4775 ] Packing sdram param for instance[9]
[   5.4775 ] Packing sdram param for instance[10]
[   5.4775 ] Packing sdram param for instance[11]
[   5.4776 ] Packing sdram param for instance[12]
[   5.4776 ] Packing sdram param for instance[13]
[   5.4777 ] Packing sdram param for instance[14]
[   5.4777 ] Packing sdram param for instance[15]
[   5.5366 ] Reading ramcode from backup chip_info.bin file
[   5.5366 ] RAMCODE Read from Device: 0

[   5.5366 ] Using ramcode 0
[   5.5366 ] Disabled BPMP dtb trim, using default dtb
[   5.5366 ] 
[   5.5372 ] tegrahost_v2 --chip 0x23 0 --align mem_rcm_aligned.bct
[   5.5376 ] tegrahost_v2 --chip 0x23 0 --magicid MEM0 --ratchet_blob ratchet_blob.bin --appendsigheader mem_rcm_aligned.bct zerosbk
[   5.5377 ] adding BCH for mem_rcm_aligned.bct
[   5.5400 ] tegrasign_v3.py --key None --list mem_rcm_aligned_sigheader.bct_list.xml --pubkeyhash pub_key.key --sha sha512
[   5.5401 ] Assuming zero filled SBK key
[   5.5412 ] Warning: pub_key.key is not found
[   5.5411 ] tegrahost_v2 --chip 0x23 0 --updatesigheader mem_rcm_aligned_sigheader.bct.encrypt mem_rcm_aligned_sigheader.bct.hash zerosbk
[   5.5418 ] Copying signatures
[   5.5419 ] tegrahost_v2 --chip 0x23 0 --partitionlayout flash.xml.bin --updatesig images_list_signed.xml
[   5.6724 ] tegraparser_v2 --generategpt --pt flash.xml.bin
[   5.6726 ] gpt_secondary_3_0.bin:
[   5.6730 ] partition_id	partition_name			      StartingLba	EndingLba
[   5.6732 ]            1	BCT                                 	       0    2047
[   5.6733 ]            2	A_mb1                               	    2048    3071
[   5.6735 ]            3	A_psc_bl1                           	    3072    3583
[   5.6737 ]            4	A_MB1_BCT                           	    3584    3839
[   5.6739 ]            5	A_MEM_BCT                           	    3840    4351
[   5.6740 ]            6	A_tsec-fw                           	    4352    6399
[   5.6742 ]            7	A_nvdec                             	    6400    8447
[   5.6744 ]            8	A_mb2                               	    8448    9471
[   5.6746 ]            9	A_xusb-fw                           	    9472    9983
[   5.6748 ]           10	A_bpmp-fw                           	    9984   13055
[   5.6749 ]           11	A_bpmp-fw-dtb                       	   13056   21247
[   5.6751 ]           12	A_psc-fw                            	   21248   22783
[   5.6753 ]           13	A_mts-mce                           	   22784   23807
[   5.6755 ]           14	A_sc7                               	   23808   24191
[   5.6757 ]           15	A_pscrf                             	   24192   24575
[   5.6759 ]           16	A_mb2rf                             	   24576   24831
[   5.6760 ]           17	A_cpu-bootloader                    	   24832   31999
[   5.6762 ]           18	A_secure-os                         	   32000   40191
[   5.6764 ]           19	A_smm-fw                            	   40192   44287
[   5.6765 ]           20	A_eks                               	   44288   44799
[   5.6766 ]           21	A_dce-fw                            	   44800   55039
[   5.6766 ]           22	A_spe-fw                            	   55040   56191
[   5.6767 ]           23	A_rce-fw                            	   56192   58239
[   5.6768 ]           24	A_adsp-fw                           	   58240   62335
[   5.6769 ]           25	A_pva-fw                            	   62336   62847
[   5.6770 ]           26	A_reserved_on_boot                  	   62848   65023
[   5.6771 ]           27	B_mb1                               	   65024   66047
[   5.6772 ]           28	B_psc_bl1                           	   66048   66559
[   5.6773 ]           29	B_MB1_BCT                           	   66560   66815
[   5.6773 ]           30	B_MEM_BCT                           	   66816   67327
[   5.6774 ]           31	B_tsec-fw                           	   67328   69375
[   5.6775 ]           32	B_nvdec                             	   69376   71423
[   5.6777 ]           33	B_mb2                               	   71424   72447
[   5.6777 ]           34	B_xusb-fw                           	   72448   72959
[   5.6778 ]           35	B_bpmp-fw                           	   72960   76031
[   5.6779 ]           36	B_bpmp-fw-dtb                       	   76032   84223
[   5.6780 ]           37	B_psc-fw                            	   84224   85759
[   5.6781 ]           38	B_mts-mce                           	   85760   86783
[   5.6782 ]           39	B_sc7                               	   86784   87167
[   5.6782 ]           40	B_pscrf                             	   87168   87551
[   5.6783 ]           41	B_mb2rf                             	   87552   87807
[   5.6784 ]           42	B_cpu-bootloader                    	   87808   94975
[   5.6785 ]           43	B_secure-os                         	   94976  103167
[   5.6786 ]           44	B_smm-fw                            	  103168  107263
[   5.6786 ]           45	B_eks                               	  107264  107775
[   5.6787 ]           46	B_dce-fw                            	  107776  118015
[   5.6788 ]           47	B_spe-fw                            	  118016  119167
[   5.6789 ]           48	B_rce-fw                            	  119168  121215
[   5.6790 ]           49	B_adsp-fw                           	  121216  125311
[   5.6791 ]           50	B_pva-fw                            	  125312  125823
[   5.6791 ]           51	B_reserved_on_boot                  	  125824  127999
[   5.6792 ]           52	uefi_variables                      	  128000  128511
[   5.6793 ]           53	uefi_ftw                            	  128512  129535
[   5.6794 ]           54	reserved                            	  129536  129919
[   5.6795 ]           55	worm                                	  129920  130303
[   5.6796 ]           56	BCT-boot-chain_backup               	  130304  130431
[   5.6797 ]           57	reserved_partition                  	  130432  130559
[   5.6797 ]           58	secondary_gpt_backup                	  130560  130687
[   5.6798 ]           59	B_VER                               	  130688  130815
[   5.6799 ]           60	A_VER                               	  130816  130943
[   5.6884 ] Get magic id
[   5.6887 ] tegraparser_v2 --get_magic psc_fw
[   5.6889 ] PFWP
[   5.6890 ] partition type psc_fw, magic id = PFWP
[   5.6898 ] tegrahost_v2 --chip 0x23 0 --align pscfw_t234_prod_aligned.bin
[   5.6904 ] tegrahost_v2 --chip 0x23 0 --magicid PFWP --ratchet_blob ratchet_blob.bin --appendsigheader pscfw_t234_prod_aligned.bin zerosbk
[   5.6906 ] Header already present for pscfw_t234_prod_aligned.bin
[   5.6943 ] tegrasign_v3.py --key None --list pscfw_t234_prod_aligned_sigheader.bin_list.xml --pubkeyhash pub_key.key --sha sha512
[   5.6944 ] Assuming zero filled SBK key
[   5.6958 ] Warning: pub_key.key is not found
[   5.6957 ] tegrahost_v2 --chip 0x23 0 --updatesigheader pscfw_t234_prod_aligned_sigheader.bin.encrypt pscfw_t234_prod_aligned_sigheader.bin.hash zerosbk
[   5.6969 ] Get magic id
[   5.6972 ] tegraparser_v2 --get_magic mts_mce
[   5.6974 ] MTSM
[   5.6975 ] partition type mts_mce, magic id = MTSM
[   5.6980 ] tegrahost_v2 --chip 0x23 0 --align mce_flash_o10_cr_prod_aligned.bin
[   5.6986 ] tegrahost_v2 --chip 0x23 0 --magicid MTSM --ratchet_blob ratchet_blob.bin --appendsigheader mce_flash_o10_cr_prod_aligned.bin zerosbk
[   5.6988 ] Header already present for mce_flash_o10_cr_prod_aligned.bin
[   5.7010 ] tegrasign_v3.py --key None --list mce_flash_o10_cr_prod_aligned_sigheader.bin_list.xml --pubkeyhash pub_key.key --sha sha512
[   5.7011 ] Assuming zero filled SBK key
[   5.7019 ] Warning: pub_key.key is not found
[   5.7017 ] tegrahost_v2 --chip 0x23 0 --updatesigheader mce_flash_o10_cr_prod_aligned_sigheader.bin.encrypt mce_flash_o10_cr_prod_aligned_sigheader.bin.hash zerosbk
[   5.7026 ] Get magic id
[   5.7027 ] tegraparser_v2 --get_magic tsec_fw
[   5.7029 ] TSEC
[   5.7030 ] partition type tsec_fw, magic id = TSEC
[   5.7035 ] tegrahost_v2 --chip 0x23 0 --align tsec_t234_aligned.bin
[   5.7040 ] tegrahost_v2 --chip 0x23 0 --magicid TSEC --ratchet_blob ratchet_blob.bin --appendsigheader tsec_t234_aligned.bin zerosbk
[   5.7042 ] Header already present for tsec_t234_aligned.bin
[   5.7071 ] tegrasign_v3.py --key None --list tsec_t234_aligned_sigheader.bin_list.xml --pubkeyhash pub_key.key --sha sha512
[   5.7072 ] Assuming zero filled SBK key
[   5.7083 ] Warning: pub_key.key is not found
[   5.7082 ] tegrahost_v2 --chip 0x23 0 --updatesigheader tsec_t234_aligned_sigheader.bin.encrypt tsec_t234_aligned_sigheader.bin.hash zerosbk
[   5.7092 ] Get magic id
[   5.7095 ] tegraparser_v2 --get_magic mb2_applet
[   5.7097 ] MB2A
[   5.7098 ] partition type mb2_applet, magic id = MB2A
[   5.7103 ] tegrahost_v2 --chip 0x23 0 --align applet_t234_aligned.bin
[   5.7108 ] tegrahost_v2 --chip 0x23 0 --magicid MB2A --ratchet_blob ratchet_blob.bin --appendsigheader applet_t234_aligned.bin zerosbk
[   5.7110 ] adding BCH for applet_t234_aligned.bin
[   5.7163 ] tegrasign_v3.py --key None --list applet_t234_aligned_sigheader.bin_list.xml --pubkeyhash pub_key.key --sha sha512
[   5.7164 ] Assuming zero filled SBK key
[   5.7175 ] Warning: pub_key.key is not found
[   5.7174 ] tegrahost_v2 --chip 0x23 0 --updatesigheader applet_t234_aligned_sigheader.bin.encrypt applet_t234_aligned_sigheader.bin.hash zerosbk
[   5.7187 ] Generating recovery mb2-bct
[   5.7187 ] tegrabct_v2 --chip 0x23 0 --mb2bct mb2_bct.cfg --recov --mb2bctcfg tegra234-mb2-bct-misc-p3701-0000_cpp.dtb --scr tegra234-mb2-bct-scr-p3701-0000_cpp.dtb
[   5.7190 ] ERROR: value 0x31 is out of range
[   5.7198 ] ERROR: value 0x31 is out of range
[   5.7199 ] ERROR: value 0x31 is out of range
[   5.7199 ] ERROR: value 0x31 is out of range
[   5.7200 ] WARNING: unknown property 'tfc_version'
[   5.7203 ] WARNING: unknown property 'addr_header_version'
[   5.7313 ] Updating mb2-bct with storage information for RCM
[   5.7315 ] tegrabct_v2 --chip 0x23 0 --mb2bct mb2_bct_MB2.bct --updatestorageinfo flash.xml.bin
[   5.8231 ] Concatenating mb2-bct to mb2 binary
[   5.8231 ] mb2_bin_file = mb2_t234.bin
[   5.8231 ] mb2_bct_file = mb2_bct_MB2.bct
[   5.8249 ] Get magic id
[   5.8251 ] tegraparser_v2 --get_magic mb2_bootloader
[   5.8253 ] MB2B
[   5.8255 ] partition type mb2_bootloader, magic id = MB2B
[   5.8261 ] tegrahost_v2 --chip 0x23 0 --align mb2_t234_with_mb2_bct_MB2_aligned.bin
[   5.8268 ] tegrahost_v2 --chip 0x23 0 --magicid MB2B --ratchet_blob ratchet_blob.bin --appendsigheader mb2_t234_with_mb2_bct_MB2_aligned.bin zerosbk
[   5.8270 ] adding BCH for mb2_t234_with_mb2_bct_MB2_aligned.bin
[   5.8382 ] tegrasign_v3.py --key None --list mb2_t234_with_mb2_bct_MB2_aligned_sigheader.bin_list.xml --pubkeyhash pub_key.key --sha sha512
[   5.8383 ] Assuming zero filled SBK key
[   5.8397 ] Warning: pub_key.key is not found
[   5.8396 ] tegrahost_v2 --chip 0x23 0 --updatesigheader mb2_t234_with_mb2_bct_MB2_aligned_sigheader.bin.encrypt mb2_t234_with_mb2_bct_MB2_aligned_sigheader.bin.hash zerosbk
[   5.8409 ] Get magic id
[   5.8411 ] tegraparser_v2 --get_magic xusb_fw
[   5.8413 ] XUSB
[   5.8414 ] partition type xusb_fw, magic id = XUSB
[   5.8419 ] tegrahost_v2 --chip 0x23 0 --align xusb_t234_prod_aligned.bin
[   5.8424 ] tegrahost_v2 --chip 0x23 0 --magicid XUSB --ratchet_blob ratchet_blob.bin --appendsigheader xusb_t234_prod_aligned.bin zerosbk
[   5.8426 ] adding BCH for xusb_t234_prod_aligned.bin
[   5.8457 ] tegrasign_v3.py --key None --list xusb_t234_prod_aligned_sigheader.bin_list.xml --pubkeyhash pub_key.key --sha sha512
[   5.8458 ] Assuming zero filled SBK key
[   5.8466 ] Warning: pub_key.key is not found
[   5.8463 ] tegrahost_v2 --chip 0x23 0 --updatesigheader xusb_t234_prod_aligned_sigheader.bin.encrypt xusb_t234_prod_aligned_sigheader.bin.hash zerosbk
[   5.8471 ] Get magic id
[   5.8472 ] tegraparser_v2 --get_magic pva_fw
[   5.8474 ] PVAF
[   5.8475 ] partition type pva_fw, magic id = PVAF
[   5.8494 ] tegrahost_v2 --chip 0x23 0 --align nvpva_020_aligned.fw
[   5.8498 ] tegrahost_v2 --chip 0x23 0 --magicid PVAF --ratchet_blob ratchet_blob.bin --appendsigheader nvpva_020_aligned.fw zerosbk
[   5.8499 ] adding BCH for nvpva_020_aligned.fw
[   5.8835 ] tegrasign_v3.py --key None --list nvpva_020_aligned_sigheader.fw_list.xml --pubkeyhash pub_key.key --sha sha512
[   5.8836 ] Assuming zero filled SBK key
[   5.8859 ] Warning: pub_key.key is not found
[   5.8858 ] tegrahost_v2 --chip 0x23 0 --updatesigheader nvpva_020_aligned_sigheader.fw.encrypt nvpva_020_aligned_sigheader.fw.hash zerosbk
[   5.8891 ] Kernel DTB used: tegra234-p3737-0000+p3701-0004-nv_with_odm_overlay.dtb.updated
[   5.8891 ] Concatenating kernel-dtb to dce-fw binary
[   5.8891 ] dce_bin = display-t234-dce.bin
[   5.8891 ] kernel_dtb = tegra234-p3737-0000+p3701-0004-nv_with_odm_overlay.dtb.updated
[   5.8891 ] dce_with_dtb = display-t234-dce_with_tegra234-p3737-0000+p3701-0004-nv_with_odm_overlay.dtb.bin
[   6.4188 ] Get magic id
[   6.4192 ] tegraparser_v2 --get_magic dce_fw
[   6.4194 ] DCEF
[   6.4196 ] partition type dce_fw, magic id = DCEF
[   6.5253 ] tegrahost_v2 --chip 0x23 0 --align display-t234-dce_with_tegra234-p3737-0000+p3701-0004-nv_with_odm_overlay.dtb_aligned.bin
[   6.5260 ] tegrahost_v2 --chip 0x23 0 --magicid DCEF --ratchet_blob ratchet_blob.bin --appendsigheader display-t234-dce_with_tegra234-p3737-0000+p3701-0004-nv_with_odm_overlay.dtb_aligned.bin zerosbk
[   6.5263 ] adding BCH for display-t234-dce_with_tegra234-p3737-0000+p3701-0004-nv_with_odm_overlay.dtb_aligned.bin
[   6.7127 ] tegrasign_v3.py --key None --list display-t234-dce_with_tegra234-p3737-0000+p3701-0004-nv_with_odm_overlay.dtb_aligned_sigheader.bin_list.xml --pubkeyhash pub_key.key --sha sha512
[   6.7128 ] Assuming zero filled SBK key
[   6.7291 ] Warning: pub_key.key is not found
[   6.7291 ] tegrahost_v2 --chip 0x23 0 --updatesigheader display-t234-dce_with_tegra234-p3737-0000+p3701-0004-nv_with_odm_overlay.dtb_aligned_sigheader.bin.encrypt display-t234-dce_with_tegra234-p3737-0000+p3701-0004-nv_with_odm_overlay.dtb_aligned_sigheader.bin.hash zerosbk
[   6.7475 ] Get magic id
[   6.7479 ] tegraparser_v2 --get_magic nvdec
[   6.7481 ] NDEC
[   6.7482 ] partition type nvdec, magic id = NDEC
[   6.7489 ] tegrahost_v2 --chip 0x23 0 --align nvdec_t234_prod_aligned.fw
[   6.7495 ] tegrahost_v2 --chip 0x23 0 --magicid NDEC --ratchet_blob ratchet_blob.bin --appendsigheader nvdec_t234_prod_aligned.fw zerosbk
[   6.7497 ] Header already present for nvdec_t234_prod_aligned.fw
[   6.7886 ] tegrasign_v3.py --key None --list nvdec_t234_prod_aligned_sigheader.fw_list.xml --pubkeyhash pub_key.key --sha sha512
[   6.7888 ] Assuming zero filled SBK key
[   6.7903 ] Warning: pub_key.key is not found
[   6.7902 ] tegrahost_v2 --chip 0x23 0 --updatesigheader nvdec_t234_prod_aligned_sigheader.fw.encrypt nvdec_t234_prod_aligned_sigheader.fw.hash zerosbk
[   6.7914 ] Get magic id
[   6.7917 ] tegraparser_v2 --get_magic bpmp_fw
[   6.7919 ] BPMF
[   6.7920 ] partition type bpmp_fw, magic id = BPMF
[   6.8762 ] tegrahost_v2 --chip 0x23 0 --align bpmp_t234-TE990M-A1_prod_aligned.bin
[   6.8766 ] tegrahost_v2 --chip 0x23 0 --magicid BPMF --ratchet_blob ratchet_blob.bin --appendsigheader bpmp_t234-TE990M-A1_prod_aligned.bin zerosbk
[   6.8767 ] Header already present for bpmp_t234-TE990M-A1_prod_aligned.bin
[   6.8856 ] tegrasign_v3.py --key None --list bpmp_t234-TE990M-A1_prod_aligned_sigheader.bin_list.xml --pubkeyhash pub_key.key --sha sha512
[   6.8857 ] Assuming zero filled SBK key
[   6.8882 ] Warning: pub_key.key is not found
[   6.8881 ] tegrahost_v2 --chip 0x23 0 --updatesigheader bpmp_t234-TE990M-A1_prod_aligned_sigheader.bin.encrypt bpmp_t234-TE990M-A1_prod_aligned_sigheader.bin.hash zerosbk
[   6.8905 ] Using bpmp-dtb concatenated with odmdata
[   6.8905 ] Get magic id
[   6.8908 ] tegraparser_v2 --get_magic bpmp_fw_dtb
[   6.8910 ] BPMD
[   6.8912 ] partition type bpmp_fw_dtb, magic id = BPMD
[   6.8919 ] tegrahost_v2 --chip 0x23 0 --align tegra234-bpmp-3701-0004-3737-0000_with_odm_aligned.dtb
[   6.8925 ] tegrahost_v2 --chip 0x23 0 --magicid BPMD --ratchet_blob ratchet_blob.bin --appendsigheader tegra234-bpmp-3701-0004-3737-0000_with_odm_aligned.dtb zerosbk
[   6.8927 ] adding BCH for tegra234-bpmp-3701-0004-3737-0000_with_odm_aligned.dtb
[   6.9007 ] tegrasign_v3.py --key None --list tegra234-bpmp-3701-0004-3737-0000_with_odm_aligned_sigheader.dtb_list.xml --pubkeyhash pub_key.key --sha sha512
[   6.9008 ] Assuming zero filled SBK key
[   6.9020 ] Warning: pub_key.key is not found
[   6.9019 ] tegrahost_v2 --chip 0x23 0 --updatesigheader tegra234-bpmp-3701-0004-3737-0000_with_odm_aligned_sigheader.dtb.encrypt tegra234-bpmp-3701-0004-3737-0000_with_odm_aligned_sigheader.dtb.hash zerosbk
[   6.9032 ] Get magic id
[   6.9035 ] tegraparser_v2 --get_magic rce_fw
[   6.9037 ] RCEF
[   6.9038 ] partition type rce_fw, magic id = RCEF
[   6.9044 ] tegrahost_v2 --chip 0x23 0 --align camera-rtcpu-t234-rce_aligned.img
[   6.9050 ] tegrahost_v2 --chip 0x23 0 --magicid RCEF --ratchet_blob ratchet_blob.bin --appendsigheader camera-rtcpu-t234-rce_aligned.img zerosbk
[   6.9052 ] adding BCH for camera-rtcpu-t234-rce_aligned.img
[   6.9132 ] tegrasign_v3.py --key None --list camera-rtcpu-t234-rce_aligned_sigheader.img_list.xml --pubkeyhash pub_key.key --sha sha512
[   6.9133 ] Assuming zero filled SBK key
[   6.9144 ] Warning: pub_key.key is not found
[   6.9142 ] tegrahost_v2 --chip 0x23 0 --updatesigheader camera-rtcpu-t234-rce_aligned_sigheader.img.encrypt camera-rtcpu-t234-rce_aligned_sigheader.img.hash zerosbk
[   6.9154 ] Get magic id
[   6.9157 ] tegraparser_v2 --get_magic ape_fw
[   6.9158 ] APEF
[   6.9160 ] partition type ape_fw, magic id = APEF
[   6.9167 ] tegrahost_v2 --chip 0x23 0 --align adsp-fw_aligned.bin
[   6.9173 ] tegrahost_v2 --chip 0x23 0 --magicid APEF --ratchet_blob ratchet_blob.bin --appendsigheader adsp-fw_aligned.bin zerosbk
[   6.9175 ] adding BCH for adsp-fw_aligned.bin
[   6.9251 ] tegrasign_v3.py --key None --list adsp-fw_aligned_sigheader.bin_list.xml --pubkeyhash pub_key.key --sha sha512
[   6.9253 ] Assuming zero filled SBK key
[   6.9265 ] Warning: pub_key.key is not found
[   6.9263 ] tegrahost_v2 --chip 0x23 0 --updatesigheader adsp-fw_aligned_sigheader.bin.encrypt adsp-fw_aligned_sigheader.bin.hash zerosbk
[   6.9762 ] Get magic id
[   6.9766 ] tegraparser_v2 --get_magic spe_fw
[   6.9768 ] SPEF
[   6.9771 ] partition type spe_fw, magic id = SPEF
[   6.9777 ] tegrahost_v2 --chip 0x23 0 --align spe_t234_aligned.bin
[   6.9784 ] tegrahost_v2 --chip 0x23 0 --magicid SPEF --ratchet_blob ratchet_blob.bin --appendsigheader spe_t234_aligned.bin zerosbk
[   6.9786 ] adding BCH for spe_t234_aligned.bin
[   6.9837 ] tegrasign_v3.py --key None --list spe_t234_aligned_sigheader.bin_list.xml --pubkeyhash pub_key.key --sha sha512
[   6.9838 ] Assuming zero filled SBK key
[   6.9848 ] Warning: pub_key.key is not found
[   6.9847 ] tegrahost_v2 --chip 0x23 0 --updatesigheader spe_t234_aligned_sigheader.bin.encrypt spe_t234_aligned_sigheader.bin.hash zerosbk
[   6.9856 ] Get magic id
[   6.9858 ] tegraparser_v2 --get_magic tos
[   6.9860 ] TOSB
[   6.9861 ] partition type tos, magic id = TOSB
[   6.9874 ] tegrahost_v2 --chip 0x23 0 --align tos-optee_t234_aligned.img
[   6.9878 ] tegrahost_v2 --chip 0x23 0 --magicid TOSB --ratchet_blob ratchet_blob.bin --appendsigheader tos-optee_t234_aligned.img zerosbk
[   6.9879 ] adding BCH for tos-optee_t234_aligned.img
[   7.0136 ] tegrasign_v3.py --key None --list tos-optee_t234_aligned_sigheader.img_list.xml --pubkeyhash pub_key.key --sha sha512
[   7.0137 ] Assuming zero filled SBK key
[   7.0159 ] Warning: pub_key.key is not found
[   7.0158 ] tegrahost_v2 --chip 0x23 0 --updatesigheader tos-optee_t234_aligned_sigheader.img.encrypt tos-optee_t234_aligned_sigheader.img.hash zerosbk
[   7.0186 ] Get magic id
[   7.0188 ] tegraparser_v2 --get_magic eks
[   7.0190 ] EKSB
[   7.0191 ] partition type eks, magic id = EKSB
[   7.0196 ] tegrahost_v2 --chip 0x23 0 --align eks_t234_aligned.img
[   7.0202 ] tegrahost_v2 --chip 0x23 0 --magicid EKSB --ratchet_blob ratchet_blob.bin --appendsigheader eks_t234_aligned.img zerosbk
[   7.0204 ] adding BCH for eks_t234_aligned.img
[   7.0214 ] tegrasign_v3.py --key None --list eks_t234_aligned_sigheader.img_list.xml --pubkeyhash pub_key.key --sha sha512
[   7.0215 ] Assuming zero filled SBK key
[   7.0225 ] Warning: pub_key.key is not found
[   7.0224 ] tegrahost_v2 --chip 0x23 0 --updatesigheader eks_t234_aligned_sigheader.img.encrypt eks_t234_aligned_sigheader.img.hash zerosbk
[   7.1248 ] tegrahost_v2 --chip 0x23 0 --align uefi_jetson_with_dtb_aligned.bin
[   7.1254 ] tegrahost_v2 --chip 0x23 0 --magicid CPBL --ratchet_blob ratchet_blob.bin --appendsigheader uefi_jetson_with_dtb_aligned.bin zerosbk
[   7.1257 ] adding BCH for uefi_jetson_with_dtb_aligned.bin
[   7.1859 ] tegrasign_v3.py --key None --list uefi_jetson_with_dtb_aligned_sigheader.bin_list.xml --pubkeyhash pub_key.key --sha sha512
[   7.1860 ] Assuming zero filled SBK key
[   7.1900 ] Warning: pub_key.key is not found
[   7.1900 ] tegrahost_v2 --chip 0x23 0 --updatesigheader uefi_jetson_with_dtb_aligned_sigheader.bin.encrypt uefi_jetson_with_dtb_aligned_sigheader.bin.hash zerosbk
[   7.1951 ] Copying enc\/signed file in /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.2711 ] Copying br bct for multi chains
[   7.2712 ] Signed BCT for boot chain A is copied to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/br_bct_BR.bct

[   7.2712 ] Signed BCT for boot chain B is copied to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/br_bct_b_BR.bct

[   7.2712 ] Copying BCT backup image bct_backup.img to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/bct_backup.img
[   7.2726 ] Copying pscfw_t234_prod_sigheader.bin.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.3302 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/pscfw_t234_prod_sigheader.bin.encrypt
[   7.3302 ] Copying mce_flash_o10_cr_prod_sigheader.bin.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.3303 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/mce_flash_o10_cr_prod_sigheader.bin.encrypt
[   7.3304 ] Copying tsec_t234_sigheader.bin.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.3304 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/tsec_t234_sigheader.bin.encrypt
[   7.3304 ] Copying applet_t234_sigheader.bin.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.3306 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/applet_t234_sigheader.bin.encrypt
[   7.3306 ] Copying mb2_t234_with_mb2_bct_MB2_sigheader.bin.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.3307 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/mb2_t234_with_mb2_bct_MB2_sigheader.bin.encrypt
[   7.3307 ] Copying xusb_t234_prod_sigheader.bin.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.3308 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/xusb_t234_prod_sigheader.bin.encrypt
[   7.3308 ] Copying nvpva_020_sigheader.fw.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.3315 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/nvpva_020_sigheader.fw.encrypt
[   7.3315 ] Copying display-t234-dce_sigheader.bin.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.3349 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/display-t234-dce_sigheader.bin.encrypt
[   7.3349 ] Copying display-t234-dce_with_tegra234-p3737-0000+p3701-0004-nv_with_odm_overlay.dtb_sigheader.bin.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.3384 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/display-t234-dce_with_tegra234-p3737-0000+p3701-0004-nv_with_odm_overlay.dtb_sigheader.bin.encrypt
[   7.3384 ] Copying nvdec_t234_prod_sigheader.fw.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.3385 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/nvdec_t234_prod_sigheader.fw.encrypt
[   7.3385 ] Copying bpmp_t234-TE990M-A1_prod_sigheader.bin.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.3390 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/bpmp_t234-TE990M-A1_prod_sigheader.bin.encrypt
[   7.3390 ] Copying tegra234-bpmp-3701-0004-3737-0000_with_odm_sigheader.dtb.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.3392 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/tegra234-bpmp-3701-0004-3737-0000_with_odm_sigheader.dtb.encrypt
[   7.3392 ] Copying camera-rtcpu-t234-rce_sigheader.img.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.3394 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/camera-rtcpu-t234-rce_sigheader.img.encrypt
[   7.3394 ] Copying adsp-fw_sigheader.bin.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.3396 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/adsp-fw_sigheader.bin.encrypt
[   7.3396 ] Copying spe_t234_sigheader.bin.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.3397 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/spe_t234_sigheader.bin.encrypt
[   7.3397 ] Copying tos-optee_t234_sigheader.img.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.3404 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/tos-optee_t234_sigheader.img.encrypt
[   7.3404 ] Copying eks_t234_sigheader.img.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.4432 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/eks_t234_sigheader.img.encrypt
[   7.4432 ] Copying uefi_jetson_with_dtb_sigheader.bin.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.4444 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/uefi_jetson_with_dtb_sigheader.bin.encrypt
[   7.4459 ] tegraparser_v2 --pt flash.xml.bin --generateflashindex /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/flash.xml.tmp flash.idx
Using bpmp-dtb concatenated with odmdata in blob for t23x
./tegraflash.py --bl uefi_jetson_with_dtb_sigheader.bin.encrypt --bct br_bct_BR.bct --bldtb tegra234-p3737-0000+p3701-0004-nv.dtb --applet rcm_2_encrypt.rcm --applet_softfuse rcm_1_encrypt.rcm --cmd "secureflash;reboot"  --cfg secureflash.xml --chip 0x23 --mb1_bct mb1_bct_MB1_sigheader.bct.encrypt --mem_bct mem_rcm_sigheader.bct.encrypt --mb1_cold_boot_bct mb1_cold_boot_bct_MB1_sigheader.bct.encrypt --mb1_bin mb1_t234_prod_aligned_sigheader.bin.encrypt --psc_bl1_bin psc_bl1_t234_prod_aligned_sigheader.bin.encrypt --mem_bct_cold_boot mem_coldboot_sigheader.bct.encrypt  --bins "psc_fw pscfw_t234_prod_sigheader.bin.encrypt; mts_mce mce_flash_o10_cr_prod_sigheader.bin.encrypt; tsec_fw tsec_t234_sigheader.bin.encrypt; mb2_applet applet_t234_sigheader.bin.encrypt; mb2_bootloader mb2_t234_with_mb2_bct_MB2_sigheader.bin.encrypt; xusb_fw xusb_t234_prod_sigheader.bin.encrypt; pva_fw nvpva_020_sigheader.fw.encrypt; dce_fw display-t234-dce_sigheader.bin.encrypt; nvdec nvdec_t234_prod_sigheader.fw.encrypt; bpmp_fw bpmp_t234-TE990M-A1_prod_sigheader.bin.encrypt; bpmp_fw_dtb tegra234-bpmp-3701-0004-3737-0000_with_odm_sigheader.dtb.encrypt; rce_fw camera-rtcpu-t234-rce_sigheader.img.encrypt; ape_fw adsp-fw_sigheader.bin.encrypt; spe_fw spe_t234_sigheader.bin.encrypt; tos tos-optee_t234_sigheader.img.encrypt; eks eks_t234_sigheader.img.encrypt"    --bct_backup 
saving flash command in flashcmd.txt

*** no-flash flag enabled. Exiting now... *** 

User can run above saved command in factory environment without 
providing pkc and sbk keys to flash a device

Example:

    $ cd bootloader 
    $ sudo bash ./flashcmd.txt

'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/flash.idx' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/flash.idx'
Flash index file is /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/flash.idx
Number of lines is 61
max_index=60
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/br_bct_BR.bct  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/br_bct_BR.bct
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/br_bct_BR.bct' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/br_bct_BR.bct'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/mb1_t234_prod_aligned_sigheader.bin.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/mb1_t234_prod_aligned_sigheader.bin.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/mb1_t234_prod_aligned_sigheader.bin.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/mb1_t234_prod_aligned_sigheader.bin.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/psc_bl1_t234_prod_aligned_sigheader.bin.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/psc_bl1_t234_prod_aligned_sigheader.bin.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/psc_bl1_t234_prod_aligned_sigheader.bin.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/psc_bl1_t234_prod_aligned_sigheader.bin.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/mb1_cold_boot_bct_MB1_sigheader.bct.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/mb1_cold_boot_bct_MB1_sigheader.bct.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/mb1_cold_boot_bct_MB1_sigheader.bct.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/mb1_cold_boot_bct_MB1_sigheader.bct.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/mem_coldboot_sigheader.bct.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/mem_coldboot_sigheader.bct.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/mem_coldboot_sigheader.bct.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/mem_coldboot_sigheader.bct.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/tsec_t234_sigheader.bin.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/tsec_t234_sigheader.bin.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/tsec_t234_sigheader.bin.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/tsec_t234_sigheader.bin.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/nvdec_t234_prod_sigheader.fw.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/nvdec_t234_prod_sigheader.fw.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/nvdec_t234_prod_sigheader.fw.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/nvdec_t234_prod_sigheader.fw.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/mb2_t234_with_mb2_cold_boot_bct_MB2_sigheader.bin.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/mb2_t234_with_mb2_cold_boot_bct_MB2_sigheader.bin.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/mb2_t234_with_mb2_cold_boot_bct_MB2_sigheader.bin.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/mb2_t234_with_mb2_cold_boot_bct_MB2_sigheader.bin.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/xusb_t234_prod_sigheader.bin.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/xusb_t234_prod_sigheader.bin.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/xusb_t234_prod_sigheader.bin.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/xusb_t234_prod_sigheader.bin.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/bpmp_t234-TE990M-A1_prod_sigheader.bin.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/bpmp_t234-TE990M-A1_prod_sigheader.bin.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/bpmp_t234-TE990M-A1_prod_sigheader.bin.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/bpmp_t234-TE990M-A1_prod_sigheader.bin.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/tegra234-bpmp-3701-0004-3737-0000_with_odm_sigheader.dtb.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/tegra234-bpmp-3701-0004-3737-0000_with_odm_sigheader.dtb.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/tegra234-bpmp-3701-0004-3737-0000_with_odm_sigheader.dtb.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/tegra234-bpmp-3701-0004-3737-0000_with_odm_sigheader.dtb.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/pscfw_t234_prod_sigheader.bin.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/pscfw_t234_prod_sigheader.bin.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/pscfw_t234_prod_sigheader.bin.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/pscfw_t234_prod_sigheader.bin.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/mce_flash_o10_cr_prod_sigheader.bin.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/mce_flash_o10_cr_prod_sigheader.bin.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/mce_flash_o10_cr_prod_sigheader.bin.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/mce_flash_o10_cr_prod_sigheader.bin.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/sc7_t234_prod_sigheader.bin.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/sc7_t234_prod_sigheader.bin.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/sc7_t234_prod_sigheader.bin.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/sc7_t234_prod_sigheader.bin.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/psc_rf_t234_prod_sigheader.bin.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/psc_rf_t234_prod_sigheader.bin.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/psc_rf_t234_prod_sigheader.bin.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/psc_rf_t234_prod_sigheader.bin.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/mb2rf_t234_sigheader.bin.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/mb2rf_t234_sigheader.bin.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/mb2rf_t234_sigheader.bin.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/mb2rf_t234_sigheader.bin.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/uefi_jetson_with_dtb_aligned_blob_w_bin_sigheader.bin.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/uefi_jetson_with_dtb_aligned_blob_w_bin_sigheader.bin.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/uefi_jetson_with_dtb_aligned_blob_w_bin_sigheader.bin.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/uefi_jetson_with_dtb_aligned_blob_w_bin_sigheader.bin.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/tos-optee_t234_sigheader.img.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/tos-optee_t234_sigheader.img.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/tos-optee_t234_sigheader.img.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/tos-optee_t234_sigheader.img.encrypt'
Warning: skip writing A_smm-fw partition as no image is specified
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/eks_t234_sigheader.img.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/eks_t234_sigheader.img.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/eks_t234_sigheader.img.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/eks_t234_sigheader.img.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/display-t234-dce_with_tegra234-p3737-0000+p3701-0004-nv_with_odm_overlay.dtb_aligned_blob_w_bin_sigheader.bin.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/display-t234-dce_with_tegra234-p3737-0000+p3701-0004-nv_with_odm_overlay.dtb_aligned_blob_w_bin_sigheader.bin.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/display-t234-dce_with_tegra234-p3737-0000+p3701-0004-nv_with_odm_overlay.dtb_aligned_blob_w_bin_sigheader.bin.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/display-t234-dce_with_tegra234-p3737-0000+p3701-0004-nv_with_odm_overlay.dtb_aligned_blob_w_bin_sigheader.bin.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/spe_t234_sigheader.bin.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/spe_t234_sigheader.bin.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/spe_t234_sigheader.bin.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/spe_t234_sigheader.bin.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/camera-rtcpu-t234-rce_sigheader.img.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/camera-rtcpu-t234-rce_sigheader.img.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/camera-rtcpu-t234-rce_sigheader.img.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/camera-rtcpu-t234-rce_sigheader.img.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/adsp-fw_sigheader.bin.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/adsp-fw_sigheader.bin.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/adsp-fw_sigheader.bin.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/adsp-fw_sigheader.bin.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/nvpva_020_aligned_blob_w_bin_sigheader.fw.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/nvpva_020_aligned_blob_w_bin_sigheader.fw.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/nvpva_020_aligned_blob_w_bin_sigheader.fw.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/nvpva_020_aligned_blob_w_bin_sigheader.fw.encrypt'
Warning: skip writing A_reserved_on_boot partition as no image is specified
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/mb1_t234_prod_aligned_sigheader.bin.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/mb1_t234_prod_aligned_sigheader.bin.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/mb1_t234_prod_aligned_sigheader.bin.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/mb1_t234_prod_aligned_sigheader.bin.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/psc_bl1_t234_prod_aligned_sigheader.bin.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/psc_bl1_t234_prod_aligned_sigheader.bin.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/psc_bl1_t234_prod_aligned_sigheader.bin.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/psc_bl1_t234_prod_aligned_sigheader.bin.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/mb1_cold_boot_bct_MB1_sigheader.bct.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/mb1_cold_boot_bct_MB1_sigheader.bct.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/mb1_cold_boot_bct_MB1_sigheader.bct.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/mb1_cold_boot_bct_MB1_sigheader.bct.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/mem_coldboot_sigheader.bct.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/mem_coldboot_sigheader.bct.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/mem_coldboot_sigheader.bct.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/mem_coldboot_sigheader.bct.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/tsec_t234_sigheader.bin.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/tsec_t234_sigheader.bin.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/tsec_t234_sigheader.bin.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/tsec_t234_sigheader.bin.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/nvdec_t234_prod_sigheader.fw.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/nvdec_t234_prod_sigheader.fw.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/nvdec_t234_prod_sigheader.fw.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/nvdec_t234_prod_sigheader.fw.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/mb2_t234_with_mb2_cold_boot_bct_MB2_sigheader.bin.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/mb2_t234_with_mb2_cold_boot_bct_MB2_sigheader.bin.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/mb2_t234_with_mb2_cold_boot_bct_MB2_sigheader.bin.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/mb2_t234_with_mb2_cold_boot_bct_MB2_sigheader.bin.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/xusb_t234_prod_sigheader.bin.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/xusb_t234_prod_sigheader.bin.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/xusb_t234_prod_sigheader.bin.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/xusb_t234_prod_sigheader.bin.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/bpmp_t234-TE990M-A1_prod_sigheader.bin.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/bpmp_t234-TE990M-A1_prod_sigheader.bin.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/bpmp_t234-TE990M-A1_prod_sigheader.bin.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/bpmp_t234-TE990M-A1_prod_sigheader.bin.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/tegra234-bpmp-3701-0004-3737-0000_with_odm_sigheader.dtb.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/tegra234-bpmp-3701-0004-3737-0000_with_odm_sigheader.dtb.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/tegra234-bpmp-3701-0004-3737-0000_with_odm_sigheader.dtb.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/tegra234-bpmp-3701-0004-3737-0000_with_odm_sigheader.dtb.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/pscfw_t234_prod_sigheader.bin.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/pscfw_t234_prod_sigheader.bin.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/pscfw_t234_prod_sigheader.bin.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/pscfw_t234_prod_sigheader.bin.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/mce_flash_o10_cr_prod_sigheader.bin.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/mce_flash_o10_cr_prod_sigheader.bin.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/mce_flash_o10_cr_prod_sigheader.bin.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/mce_flash_o10_cr_prod_sigheader.bin.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/sc7_t234_prod_sigheader.bin.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/sc7_t234_prod_sigheader.bin.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/sc7_t234_prod_sigheader.bin.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/sc7_t234_prod_sigheader.bin.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/psc_rf_t234_prod_sigheader.bin.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/psc_rf_t234_prod_sigheader.bin.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/psc_rf_t234_prod_sigheader.bin.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/psc_rf_t234_prod_sigheader.bin.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/mb2rf_t234_sigheader.bin.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/mb2rf_t234_sigheader.bin.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/mb2rf_t234_sigheader.bin.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/mb2rf_t234_sigheader.bin.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/uefi_jetson_with_dtb_aligned_blob_w_bin_sigheader.bin.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/uefi_jetson_with_dtb_aligned_blob_w_bin_sigheader.bin.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/uefi_jetson_with_dtb_aligned_blob_w_bin_sigheader.bin.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/uefi_jetson_with_dtb_aligned_blob_w_bin_sigheader.bin.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/tos-optee_t234_sigheader.img.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/tos-optee_t234_sigheader.img.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/tos-optee_t234_sigheader.img.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/tos-optee_t234_sigheader.img.encrypt'
Warning: skip writing B_smm-fw partition as no image is specified
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/eks_t234_sigheader.img.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/eks_t234_sigheader.img.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/eks_t234_sigheader.img.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/eks_t234_sigheader.img.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/display-t234-dce_with_tegra234-p3737-0000+p3701-0004-nv_with_odm_overlay.dtb_aligned_blob_w_bin_sigheader.bin.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/display-t234-dce_with_tegra234-p3737-0000+p3701-0004-nv_with_odm_overlay.dtb_aligned_blob_w_bin_sigheader.bin.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/display-t234-dce_with_tegra234-p3737-0000+p3701-0004-nv_with_odm_overlay.dtb_aligned_blob_w_bin_sigheader.bin.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/display-t234-dce_with_tegra234-p3737-0000+p3701-0004-nv_with_odm_overlay.dtb_aligned_blob_w_bin_sigheader.bin.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/spe_t234_sigheader.bin.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/spe_t234_sigheader.bin.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/spe_t234_sigheader.bin.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/spe_t234_sigheader.bin.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/camera-rtcpu-t234-rce_sigheader.img.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/camera-rtcpu-t234-rce_sigheader.img.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/camera-rtcpu-t234-rce_sigheader.img.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/camera-rtcpu-t234-rce_sigheader.img.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/adsp-fw_sigheader.bin.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/adsp-fw_sigheader.bin.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/adsp-fw_sigheader.bin.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/adsp-fw_sigheader.bin.encrypt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/nvpva_020_aligned_blob_w_bin_sigheader.fw.encrypt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/nvpva_020_aligned_blob_w_bin_sigheader.fw.encrypt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/nvpva_020_aligned_blob_w_bin_sigheader.fw.encrypt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/nvpva_020_aligned_blob_w_bin_sigheader.fw.encrypt'
Warning: skip writing B_reserved_on_boot partition as no image is specified
Warning: skip writing uefi_variables partition as no image is specified
Warning: skip writing uefi_ftw partition as no image is specified
Warning: skip writing reserved partition as no image is specified
Warning: skip writing worm partition as no image is specified
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/bct_backup.img  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/bct_backup.img
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/bct_backup.img' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/bct_backup.img'
Warning: skip writing reserved_partition partition as no image is specified
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/gpt_backup_secondary_3_0.bin  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/gpt_backup_secondary_3_0.bin
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/gpt_backup_secondary_3_0.bin' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/gpt_backup_secondary_3_0.bin'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/qspi_bootblob_ver.txt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/qspi_bootblob_ver.txt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/qspi_bootblob_ver.txt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/qspi_bootblob_ver.txt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/qspi_bootblob_ver.txt  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/qspi_bootblob_ver.txt
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/qspi_bootblob_ver.txt' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/qspi_bootblob_ver.txt'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/gpt_secondary_3_0.bin  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/gpt_secondary_3_0.bin
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/gpt_secondary_3_0.bin' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/internal/gpt_secondary_3_0.bin'
Generate image for external storage devices
Generate images to be flashed
BOOTDEV=nvme0n1p1 ADDITIONAL_DTB_OVERLAY="BootOrderNvme.dtbo,"  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/flash.sh --no-flash --sign --external-device -c "tools/kernel_flash/flash_l4t_external.xml"  jetson-agx-orin-devkit nvme0n1p1

###############################################################################
# L4T BSP Information:
# R36 , REVISION: 3.0
# User release: 0.0
###############################################################################
ECID is 0x80012344705DF1172C0000000D020080
Existing emcfuse(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/fuse_t234.xml) reused.
copying emc_fuse_dev_params(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-br-bct-diag-boot.dts)... done.
copying device_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-device-p3701-0000.dts)... done.
copying misc_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-misc-p3701-0000.dts)... done.
./tegraflash.py --chip "0x23" --applet "/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/mb1_t234_prod.bin" --skipuid --cfg readinfo_t234_min_prod.xml --dev_params tegra234-br-bct-diag-boot.dts --device_config tegra234-mb1-bct-device-p3701-0000.dts --misc_config tegra234-mb1-bct-misc-p3701-0000.dts --bins "mb2_applet applet_t234.bin" --cmd "readfuses fuse_t234.bin fuse_t234.xml; dump eeprom cvm cvm.bin; dump try_custinfo custinfo_out.bin; reboot recovery" 
Welcome to Tegra Flash
version 1.0.0
Type ? or help for help and q or quit to exit
Use ! to execute system commands
 
[   0.0102 ] Reading fuses
[   0.0106 ] tegrarcm_v2 --chip 0x23 0 --ismb2applet
[   0.0108 ] File rcm_state open failed
[   0.0110 ] ERROR: failed to read rcm_state
[   0.0110 ] 
[   0.0115 ] tegrasign_v3.py --key None --getmode mode.txt
[   0.0116 ] Assuming zero filled SBK key
[   0.0113 ] Pre-processing config: tegra234-mb1-bct-device-p3701-0000.dts
[   0.0172 ] Pre-processing config: tegra234-mb1-bct-misc-p3701-0000.dts
[   0.0249 ] Parsing partition layout
[   0.0251 ] tegraparser_v2 --pt readinfo_t234_min_prod.xml.tmp
[   0.0260 ] Kernel DTB used: None
[   0.0260 ] WARNING: dce base dtb is not provided

[   0.0260 ] Parsing partition layout
[   0.0262 ] tegraparser_v2 --pt readinfo_t234_min_prod.xml.tmp
[   0.0267 ] Creating list of images to be signed
[   0.0270 ] tegrahost_v2 --chip 0x23 0 --partitionlayout readinfo_t234_min_prod.xml.bin --list images_list.xml zerosbk
[   0.0273 ] MB1: Nvheader already present is mb1_t234_prod_aligned.bin
[   0.0281 ] Header already present for mb1_t234_prod_aligned_sigheader.bin
[   0.0284 ] MB1: Nvheader already present is mb1_t234_prod_aligned.bin
[   0.0315 ] Header already present for mb1_t234_prod_aligned_sigheader.bin
[   0.0324 ] MB1: Nvheader already present is psc_bl1_t234_prod_aligned.bin
[   0.0346 ] Header already present for psc_bl1_t234_prod_aligned_sigheader.bin
[   0.0346 ] adding BCH for mb2_t234_aligned.bin
[   0.0362 ] MB1: Nvheader already present is psc_bl1_t234_prod_aligned.bin
[   0.0422 ] Header already present for psc_bl1_t234_prod_aligned_sigheader.bin
[   0.0423 ] adding BCH for mb2_t234_aligned.bin
[   0.0499 ] Filling MB1 storage info
[   0.0499 ] Parsing dev params for multi chains
[   0.0544 ] Generating br-bct
[   0.0546 ] Updating dev and MSS params in BR BCT
[   0.0546 ] tegrabct_v2 --dev_param tegra234-br-bct-diag-boot_cpp.dtb --brbct br_bct.cfg --chip 0x23 0
[   0.0550 ] Updating bl info
[   0.0551 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updateblinfo readinfo_t234_min_prod.xml.bin
[   0.0552 ] WARNING: boot chain is not completed. set to 0
[   0.0560 ] Generating signatures
[   0.0564 ] tegrasign_v3.py --key None --list images_list.xml --pubkeyhash pub_key.key --sha sha512
[   0.0565 ] Assuming zero filled SBK key
[   0.0661 ] Warning: pub_key.key is not found
[   0.0658 ] Parsing dev params for multi chains
[   0.0658 ] Generating br-bct
[   0.0660 ] Updating dev and MSS params in BR BCT
[   0.0660 ] tegrabct_v2 --dev_param tegra234-br-bct-diag-boot_cpp.dtb --brbct br_bct.cfg --chip 0x23 0
[   0.0663 ] Updating bl info
[   0.0665 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updateblinfo readinfo_t234_min_prod.xml.bin --updatesig images_list_signed.xml
[   0.0666 ] WARNING: boot chain is not completed. set to 0
[   0.0679 ] Generating SHA2 Hash
[   0.0690 ] Sha saved in br_bct_BR.sha
[   0.0686 ] Get Signed section of bct
[   0.0688 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --listbct bct_list.xml
[   0.0693 ] Signing BCT
[   0.0697 ] tegrasign_v3.py --key None --list bct_list.xml --pubkeyhash pub_key.key --sha sha512
[   0.0698 ] Assuming zero filled SBK key
[   0.0713 ] Sha saved in br_bct_BR.sha
[   0.0715 ] Warning: pub_key.key is not found
[   0.0710 ] Updating BCT with signature
[   0.0713 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updatesig bct_list_signed.xml
[   0.0716 ] Offset :4608 Len :3584
[   0.0721 ] Generating SHA2 Hash
[   0.0725 ] tegrasign_v3.py --key None --list bct_list.xml --sha sha512
[   0.0727 ] Assuming zero filled SBK key
[   0.0727 ] Assuming zero filled SBK key
[   0.0739 ] Sha saved in br_bct_BR.sha
[   0.0735 ] Updating BCT with SHA2 Hash
[   0.0737 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updatesha bct_list_signed.xml
[   0.0738 ] Offset :4608 Len :3584
[   0.0741 ] Offset :68 Len :8124
[   0.0747 ] Generating coldboot mb1-bct
[   0.0749 ] tegrabct_v2 --chip 0x23 0 --mb1bct mb1_cold_boot_bct.cfg --misc tegra234-mb1-bct-misc-p3701-0000_cpp.dtb --device tegra234-mb1-bct-device-p3701-0000_cpp.dtb
[   0.0751 ] MB1-BCT version: 0.13

[   0.0764 ] Parsing config file :tegra234-mb1-bct-device-p3701-0000_cpp.dtb 
[   0.0766 ] Added Platform Config 9 data with size :- 100
[   0.0766 ] 
[   0.0766 ] Updating mb1-bct with firmware information
[   0.0769 ] tegrabct_v2 --chip 0x23 0 --mb1bct mb1_cold_boot_bct_MB1.bct --updatefwinfo readinfo_t234_min_prod.xml.bin
[   0.0781 ] tegrahost_v2 --chip 0x23 0 --align mb1_cold_boot_bct_MB1_aligned.bct
[   0.0785 ] Generating SHA2 Hash for mb1bct
[   0.0795 ] Sha saved in mb1_cold_boot_bct_MB1_aligned.sha
[   0.0801 ] Sha saved in mb1_cold_boot_bct_MB1.sha
[   0.0799 ] tegrahost_v2 --chip 0x23 0 --magicid MBCT --appendsigheader mb1_cold_boot_bct_MB1_aligned.bct zerosbk
[   0.0801 ] adding BCH for mb1_cold_boot_bct_MB1_aligned.bct
[   0.0810 ] tegrasign_v3.py --key None --list mb1_cold_boot_bct_MB1_aligned_sigheader.bct_list.xml --pubkeyhash pub_key.key --sha sha512
[   0.0811 ] Assuming zero filled SBK key
[   0.0818 ] Warning: pub_key.key is not found
[   0.0816 ] tegrahost_v2 --chip 0x23 0 --updatesigheader mb1_cold_boot_bct_MB1_aligned_sigheader.bct.encrypt mb1_cold_boot_bct_MB1_aligned_sigheader.bct.hash zerosbk
[   0.0822 ] Generating recovery mb1-bct
[   0.0824 ] tegrabct_v2 --chip 0x23 0 --mb1bct mb1_bct.cfg --misc tegra234-mb1-bct-misc-p3701-0000_cpp.dtb --device tegra234-mb1-bct-device-p3701-0000_cpp.dtb
[   0.0825 ] MB1-BCT version: 0.13

[   0.0839 ] Parsing config file :tegra234-mb1-bct-device-p3701-0000_cpp.dtb 
[   0.0841 ] Added Platform Config 9 data with size :- 100
[   0.0841 ] 
[   0.0841 ] Updating mb1-bct with firmware information
[   0.0845 ] tegrabct_v2 --chip 0x23 0 --mb1bct mb1_bct_MB1.bct --recov --updatefwinfo readinfo_t234_min_prod.xml.bin
[   0.0857 ] tegrahost_v2 --chip 0x23 0 --align mb1_bct_MB1_aligned.bct
[   0.0860 ] Generating SHA2 Hash for mb1bct
[   0.0871 ] Sha saved in mb1_bct_MB1_aligned.sha
[   0.0878 ] Sha saved in mb1_bct_MB1.sha
[   0.0876 ] tegrahost_v2 --chip 0x23 0 --magicid MBCT --appendsigheader mb1_bct_MB1_aligned.bct zerosbk
[   0.0878 ] adding BCH for mb1_bct_MB1_aligned.bct
[   0.0888 ] tegrasign_v3.py --key None --list mb1_bct_MB1_aligned_sigheader.bct_list.xml --pubkeyhash pub_key.key --sha sha512
[   0.0889 ] Assuming zero filled SBK key
[   0.0898 ] Warning: pub_key.key is not found
[   0.0897 ] tegrahost_v2 --chip 0x23 0 --updatesigheader mb1_bct_MB1_aligned_sigheader.bct.encrypt mb1_bct_MB1_aligned_sigheader.bct.hash zerosbk
[   0.0904 ] Info: Skip generating mem_bct because sdram_config is not defined
[   0.0904 ] Info: Skip generating mem_bct because sdram_config is not defined
[   0.0904 ] Copying signatures
[   0.0907 ] tegrahost_v2 --chip 0x23 0 --partitionlayout readinfo_t234_min_prod.xml.bin --updatesig images_list_signed.xml
[   0.0956 ] mb1_t234_prod_aligned_sigheader.bin.encrypt filename is from images_list
[   0.0957 ] psc_bl1_t234_prod_aligned_sigheader.bin.encrypt filename is from images_list
[   0.0957 ] Boot Rom communication
[   0.0960 ] tegrarcm_v2 --new_session --chip 0x23 0 --uid --download bct_br br_bct_BR.bct --download mb1 mb1_t234_prod_aligned_sigheader.bin.encrypt --download psc_bl1 psc_bl1_t234_prod_aligned_sigheader.bin.encrypt --download bct_mb1 mb1_bct_MB1_sigheader.bct.encrypt
[   0.0962 ] BR_CID: 0x80012344705DF1172C0000000D020080
[   0.0970 ] Sending bct_br
[   0.0971 ] ERROR: might be timeout in USB write.
Error: Return value 3
Command tegrarcm_v2 --new_session --chip 0x23 0 --uid --download bct_br br_bct_BR.bct --download mb1 mb1_t234_prod_aligned_sigheader.bin.encrypt --download psc_bl1 psc_bl1_t234_prod_aligned_sigheader.bin.encrypt --download bct_mb1 mb1_bct_MB1_sigheader.bct.encrypt
[  10.1039 ] tegrarcm_v2 --chip 0x23 0 --ismb2applet
[  10.1046 ] tegrarcm_v2 --chip 0x23 0 --ismb2applet
[  10.1052 ] Retrieving board information
[  10.1055 ] tegrarcm_v2 --chip 0x23 0 --oem platformdetails chip chip_info.bin
[  10.1059 ] Retrieving EEPROM data
[  10.1059 ] tegrarcm_v2 --oem platformdetails eeprom cvm /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/cvm.bin --chip 0x23 0
[  10.1065 ] tegrarcm_v2 --chip 0x23 0 --ismb2applet
[  10.1071 ] tegrarcm_v2 --chip 0x23 0 --ismb2applet
[  10.1075 ] Dumping customer Info
[  10.1077 ] tegrarcm_v2 --chip 0x23 0 --oem dump bct tmp.bct
[  10.1081 ] tegrabct_v2 --brbct tmp.bct --chip 0x23 0 --custinfo /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/custinfo_out.bin
[  10.1083 ] File tmp.bct open failed
[  10.1085 ] Error: try getting custinfo fail. Moving on
[  10.1085 ] Rebooting to recovery mode
[  10.1088 ] tegrarcm_v2 --chip 0x23 0 --ismb2
[  10.1092 ] Rebooting to recovery mode
[  10.1095 ] tegrarcm_v2 --chip 0x23 0 --reboot recovery
Board ID(3701) version(500) sku(0004) revision(F.0)
Chip SKU(00:00:00:D2) ramcode(00:00:00:00) fuselevel(fuselevel_production) board_FAB(500)
Copy /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/tegra234-p3737-0000+p3701-0004-nv.dtb to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/tegra234-p3737-0000+p3701-0004-nv.dtb.rec
copying bctfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-p3701-0000-sdram-l4t.dts)... done.
copying minratchet_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-ratchet-p3701-0000.dts)... done.
copying device_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-device-p3701-0000.dts)... done.
copying misc_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-misc-p3701-0000.dts)... done.
copying pinmux_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-pinmux-p3701-0000-a04.dtsi)... done.
copying gpioint_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-gpioint-p3701-0000.dts)... done.
copying pmic_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-pmic-p3701-0005.dts)... done.
copying pmc_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-padvoltage-p3701-0000-a04.dtsi)... done.
copying deviceprod_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-cprod-p3701-0000.dts)... done.
copying prod_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-prod-p3701-0000.dts)... done.
copying scr_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb2-bct-scr-p3701-0000.dts)... done.
copying wb0sdram(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-p3701-0000-wb0sdram-l4t.dts)... done.
copying bootrom_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-reset-p3701-0000.dts)... done.
Existing uphylane_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/tegra234-mb1-bct-uphylane-si.dtsi) reused.
copying dev_params(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-br-bct-p3701-0000.dts)... done.
copying dev_params_b(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-br-bct_b-p3701-0000.dts)... done.
copying mb2bct_cfg(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb2-bct-misc-p3701-0000.dts)... done.
Existing pscfwfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/pscfw_t234_prod.bin) reused.
Existing pscbl1file(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/psc_bl1_t234_prod.bin) reused.
Existing mtsmcefile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/mce_flash_o10_cr_prod.bin) reused.
Existing tscfwfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/tsec_t234.bin) reused.
Existing mb2applet(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/applet_t234.bin) reused.
Existing bootloader(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/mb2_t234.bin) reused.
copying initrd(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/l4t_initrd.img)... done.
bl is uefi
Making Boot image... done.
Not signing of boot.img
Making recovery ramdisk for recovery image...
Re-generating recovery ramdisk for recovery image...
/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/ramdisk_tmp /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra
54794 blocks

gzip: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/Image: not in gzip format
_BASE_KERNEL_VERSION=5.15.136-tegra
cp: cannot stat '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/rootfs/usr/bin/busybox': No such file or directory
warning: cp -f /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/rootfs/usr/bin/busybox /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/ramdisk_tmp//bin/busybox
76390 blocks
Making Recovery image...
copying recdtbfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/tegra234-p3737-0000+p3701-0004-nv.dtb.rec)... done.
20+0 records in
20+0 records out
20 bytes copied, 0.000137303 s, 146 kB/s
Existing sosfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/mb1_t234_prod.bin) reused.
Existing tegraboot(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/mb2_t234.bin) reused.
Existing cpu_bootloader(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/mb2_t234.bin) reused.
Existing mb2blfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/mb2_t234.bin) reused.
Existing xusbfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/xusb_t234_prod.bin) reused.
Existing pvafile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/nvpva_020.fw) reused.
Existing dcefile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/display-t234-dce.bin) reused.
Existing nvdecfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/nvdec_t234_prod.fw) reused.
Existing psc_rf(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/psc_rf_t234_prod.bin) reused.
Existing mb2_rf(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/mb2rf_t234.bin) reused.
Existing mb1file(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/mb1_t234_prod.bin) reused.
Existing bpffile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/bpmp_t234-TE990M-A1_prod.bin) reused.
copying bpfdtbfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/tegra234-bpmp-3701-0004-3737-0000.dtb)... done.
Existing camerafw(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/camera-rtcpu-t234-rce.img) reused.
Existing apefile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/adsp-fw.bin) reused.
Existing spefile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/spe_t234.bin) reused.
Existing wb0boot(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/sc7_t234_prod.bin) reused.
Existing tosfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/tos-optee_t234.img) reused.
Existing eksfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/eks_t234.img) reused.
copying dtbfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/tegra234-p3737-0000+p3701-0004-nv.dtb)... done.
Copying nv_boot_control.conf to rootfs
	populating kernel to rootfs... done.
	populating initrd to rootfs... done.
	populating kernel_tegra234-p3737-0000+p3701-0004-nv.dtb to rootfs... done.
Making system.img... 
	populating rootfs from /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/rootfs ... 	populating /boot/extlinux/extlinux.conf ... 	Sync'ing system.img ... done.
	Converting RAW image to Sparse image... done.
system.img built successfully. 
Not signing of kernel-dtb
Existing tbcfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/uefi_jetson.bin) reused.
131072+0 records in
131072+0 records out
67108864 bytes (67 MB, 64 MiB) copied, 1.18324 s, 56.7 MB/s
	Sync'ing esp.img ... done.
copying tbcdtbfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/tegra234-p3737-0000+p3701-0004-nv.dtb)... done.
copying cfgfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/flash_l4t_t234_nvme.xml) to flash.xml... done.
Existing flashapp(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/tegraflash.py) reused.
copying overlay_dtb(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/L4TConfiguration.dtbo)... done.
copying overlay_dtb(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/tegra234-carveouts.dtbo)... done.
copying overlay_dtb(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/tegra-optee.dtbo)... done.
copying overlay_dtb(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/tegra234-p3737-camera-dual-imx274-overlay.dtbo)... done.
copying overlay_dtb(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/tegra234-p3737-camera-e3331-overlay.dtbo)... done.
copying overlay_dtb(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/tegra234-p3737-camera-e3333-overlay.dtbo)... done.
copying overlay_dtb(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/tegra234-p3737-camera-imx185-overlay.dtbo)... done.
copying overlay_dtb(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/BootOrderNvme.dtbo)... done.
/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/L4TConfiguration_updated.dts: Warning (unit_address_vs_reg): Node /fragment@0 has a unit name, but no reg property
/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/L4TConfiguration.dtbo: Warning (unit_address_vs_reg): Node /fragment@0 has a unit name, but no reg property
./tegraflash.py --bl uefi_jetson_with_dtb.bin --odmdata gbe-uphy-config-22,nvhs-uphy-config-0,hsio-uphy-config-0,gbe0-enable-10g,hsstp-lane-map-3 --overlay_dtb L4TConfiguration.dtbo,tegra234-carveouts.dtbo,tegra-optee.dtbo,tegra234-p3737-camera-dual-imx274-overlay.dtbo,tegra234-p3737-camera-e3331-overlay.dtbo,tegra234-p3737-camera-e3333-overlay.dtbo,tegra234-p3737-camera-imx185-overlay.dtbo,BootOrderNvme.dtbo, --bldtb tegra234-p3737-0000+p3701-0004-nv.dtb --applet mb1_t234_prod.bin --cmd "sign" --cfg flash.xml --chip "0x23" --concat_cpubl_bldtb --cpubl uefi_jetson.bin --minratchet_config tegra234-mb1-bct-ratchet-p3701-0000.dts --device_config tegra234-mb1-bct-device-p3701-0000.dts --misc_config tegra234-mb1-bct-misc-p3701-0000.dts --pinmux_config tegra234-mb1-bct-pinmux-p3701-0000-a04.dtsi --gpioint_config tegra234-mb1-bct-gpioint-p3701-0000.dts --pmic_config tegra234-mb1-bct-pmic-p3701-0005.dts --pmc_config tegra234-mb1-bct-padvoltage-p3701-0000-a04.dtsi --deviceprod_config tegra234-mb1-bct-cprod-p3701-0000.dts --prod_config tegra234-mb1-bct-prod-p3701-0000.dts --scr_config tegra234-mb2-bct-scr-p3701-0000.dts --wb0sdram_config tegra234-p3701-0000-wb0sdram-l4t.dts --br_cmd_config tegra234-mb1-bct-reset-p3701-0000.dts --uphy tegra234-mb1-bct-uphylane-si.dtsi --dev_params tegra234-br-bct-p3701-0000.dts,tegra234-br-bct_b-p3701-0000.dts --mb2bct_cfg tegra234-mb2-bct-misc-p3701-0000.dts --bins "psc_fw pscfw_t234_prod.bin; mts_mce mce_flash_o10_cr_prod.bin; tsec_fw tsec_t234.bin; mb2_applet applet_t234.bin; mb2_bootloader mb2_t234.bin; xusb_fw xusb_t234_prod.bin; pva_fw nvpva_020.fw; dce_fw display-t234-dce.bin; nvdec nvdec_t234_prod.fw; bpmp_fw bpmp_t234-TE990M-A1_prod.bin; bpmp_fw_dtb tegra234-bpmp-3701-0004-3737-0000.dtb; rce_fw camera-rtcpu-t234-rce.img; ape_fw adsp-fw.bin; spe_fw spe_t234.bin; tos tos-optee_t234.img; eks eks_t234.img" --sdram_config tegra234-p3701-0000-sdram-l4t.dts --cust_info custinfo_out.bin --external_device --boot_chain A 
Welcome to Tegra Flash
version 1.0.0
Type ? or help for help and q or quit to exit
Use ! to execute system commands
 
[   0.1370 ] tegrasign_v3.py --key None --getmode mode.txt
[   0.1370 ] Assuming zero filled SBK key
[   0.1277 ] Parsing partition layout
[   0.1990 ] tegraparser_v2 --pt flash.xml.tmp
[   0.3271 ] /usr/bin/python3 dtbcheck.py -c t234 -o tegra234-bpmp-3701-0004-3737-0000_with_odm.dtb tegra234-bpmp-3701-0004-3737-0000_with_odm_tmp.dtb
[   0.6005 ] Concatenating L4TConfiguration.dtbo,tegra234-carveouts.dtbo,tegra-optee.dtbo,tegra234-p3737-camera-dual-imx274-overlay.dtbo,tegra234-p3737-camera-e3331-overlay.dtbo,tegra234-p3737-camera-e3333-overlay.dtbo,tegra234-p3737-camera-imx185-overlay.dtbo,BootOrderNvme.dtbo to tegra234-p3737-0000+p3701-0004-nv_with_odm_overlay.dtb.updated
[   0.6006 ] Concatenating bl dtb to cpubl binary
[   0.6021 ] Kernel DTB used: kernel_tegra234-p3737-0000+p3701-0004-nv.dtb
[   0.6021 ] Parsing partition layout
[   0.6024 ] tegraparser_v2 --pt flash.xml.tmp
[   0.6030 ] Creating list of images to be signed
[   0.6311 ] Generating ratchet blob
[   0.6311 ] Pre-processing config: tegra234-mb1-bct-reset-p3701-0000.dts
[   0.9604 ] Pre-processing config: tegra234-mb1-bct-device-p3701-0000.dts
[   1.0305 ] Pre-processing config: tegra234-mb1-bct-cprod-p3701-0000.dts
[   1.0761 ] Pre-processing config: tegra234-mb1-bct-gpioint-p3701-0000.dts
[   1.1232 ] Pre-processing config: tegra234-mb1-bct-misc-p3701-0000.dts
[   1.3148 ] Pre-processing config: tegra234-mb1-bct-pinmux-p3701-0000-a04.dtsi
[   1.4373 ] Pre-processing config: tegra234-mb1-bct-padvoltage-p3701-0000-a04.dtsi
[   1.4622 ] Pre-processing config: tegra234-mb1-bct-pmic-p3701-0005.dts
[   1.4830 ] Pre-processing config: tegra234-mb1-bct-prod-p3701-0000.dts
[   1.5023 ] Pre-processing config: tegra234-mb2-bct-scr-p3701-0000.dts
[   1.7085 ] Pre-processing config: tegra234-p3701-0000-sdram-l4t.dts
[   3.1795 ] Pre-processing config: tegra234-mb1-bct-uphylane-si.dtsi
[   3.2787 ] Pre-processing config: tegra234-p3701-0000-wb0sdram-l4t.dts
[   4.8575 ] Pre-processing config: tegra234-mb1-bct-ratchet-p3701-0000.dts
[   4.8659 ] Generating coldboot mb1-bct
[   4.8973 ] tegrabct_v2 --chip 0x23 0 --mb1bct mb1_cold_boot_bct.cfg --misc tegra234-mb1-bct-misc-p3701-0000_cpp.dtb --wb0sdram tegra234-p3701-0000-wb0sdram-l4t_cpp.dtb --pinmux tegra234-mb1-bct-pinmux-p3701-0000-a04_cpp.dtb --pmc tegra234-mb1-bct-padvoltage-p3701-0000-a04_cpp.dtb --pmic tegra234-mb1-bct-pmic-p3701-0005_cpp.dtb --brcommand tegra234-mb1-bct-reset-p3701-0000_cpp.dtb --prod tegra234-mb1-bct-prod-p3701-0000_cpp.dtb --gpioint tegra234-mb1-bct-gpioint-p3701-0000_cpp.dtb --uphy tegra234-mb1-bct-uphylane-si_cpp.dtb --device tegra234-mb1-bct-device-p3701-0000_cpp.dtb --deviceprod tegra234-mb1-bct-cprod-p3701-0000_cpp.dtb --minratchet tegra234-mb1-bct-ratchet-p3701-0000_cpp.dtb --ratchet_blob ratchet_blob.bin
[   4.8976 ] MB1-BCT version: 0.13

[   4.8989 ] Parsing config file :tegra234-mb1-bct-pinmux-p3701-0000-a04_cpp.dtb 
[   4.8991 ] Added Platform Config 0 data with size :- 3320

[   4.9010 ] Parsing config file :tegra234-mb1-bct-padvoltage-p3701-0000-a04_cpp.dtb 
[   4.9012 ] WARNING: unknown node 'g2'
[   4.9013 ] WARNING: unknown node 'g2'
[   4.9015 ] WARNING: unknown node 'g9'
[   4.9015 ] WARNING: unknown node 'g9'
[   4.9015 ] Added Platform Config 2 data with size :- 24
[   4.9015 ] 
[   4.9015 ] Parsing config file :tegra234-mb1-bct-pmic-p3701-0005_cpp.dtb 
[   4.9015 ] Added Platform Config 4 data with size :- 580
[   4.9015 ] 
[   4.9015 ] Parsing config file :tegra234-mb1-bct-reset-p3701-0000_cpp.dtb 
[   4.9015 ] Added Platform Config 3 data with size :- 52
[   4.9015 ] 
[   4.9015 ] Parsing config file :tegra234-mb1-bct-prod-p3701-0000_cpp.dtb 
[   4.9015 ] WARNING: unknown property 'major'
[   4.9015 ] WARNING: unknown property 'minor'
[   4.9015 ] Added Platform Config 5 data with size :- 524
[   4.9015 ] 
[   4.9015 ] Parsing config file :tegra234-mb1-bct-gpioint-p3701-0000_cpp.dtb 
[   4.9015 ] WARNING: unknown property 'major'
[   4.9015 ] WARNING: unknown property 'minor'
[   4.9015 ] Added Platform Config 7 data with size :- 380
[   4.9015 ] 
[   4.9015 ] Parsing config file :tegra234-mb1-bct-uphylane-si_cpp.dtb 
[   4.9015 ] Added Platform Config 8 data with size :- 24
[   4.9015 ] 
[   4.9015 ] Parsing config file :tegra234-mb1-bct-device-p3701-0000_cpp.dtb 
[   4.9015 ] Added Platform Config 9 data with size :- 100
[   4.9015 ] 
[   4.9015 ] Parsing config file :tegra234-mb1-bct-cprod-p3701-0000_cpp.dtb 
[   4.9015 ] ModuleCount 0 NumProdNames 0
[   4.9015 ] Added Platform Config 6 data with size :- 16
[   4.9015 ] 
[   4.9015 ] Parsing config file :tegra234-mb1-bct-ratchet-p3701-0000_cpp.dtb 
[   4.9015 ] 
[   4.9016 ] Updating mb1-bct with firmware information
[   4.9019 ] tegrabct_v2 --chip 0x23 0 --mb1bct mb1_cold_boot_bct_MB1.bct --updatefwinfo flash.xml.bin
[   4.9376 ] tegrahost_v2 --chip 0x23 0 --align mb1_cold_boot_bct_MB1_aligned.bct
[   4.9381 ] Generating SHA2 Hash for mb1bct
[   4.9892 ] Sha saved in mb1_cold_boot_bct_MB1_aligned.sha
[   4.9900 ] Sha saved in mb1_cold_boot_bct_MB1.sha
[   4.9715 ] tegrahost_v2 --chip 0x23 0 --magicid MBCT --ratchet_blob ratchet_blob.bin --appendsigheader mb1_cold_boot_bct_MB1_aligned.bct zerosbk
[   4.9717 ] adding BCH for mb1_cold_boot_bct_MB1_aligned.bct
[   4.9911 ] tegrasign_v3.py --key None --list mb1_cold_boot_bct_MB1_aligned_sigheader.bct_list.xml --pubkeyhash pub_key.key --sha sha512
[   4.9912 ] Assuming zero filled SBK key
[   4.9922 ] Warning: pub_key.key is not found
[   4.9738 ] tegrahost_v2 --chip 0x23 0 --updatesigheader mb1_cold_boot_bct_MB1_aligned_sigheader.bct.encrypt mb1_cold_boot_bct_MB1_aligned_sigheader.bct.hash zerosbk
[   4.9745 ] tegrahost_v2 --chip 0x23 0 --partitionlayout flash.xml.bin --ratchet_blob ratchet_blob.bin --list images_list.xml zerosbk
[   4.9749 ] Filling MB1 storage info
[   4.9749 ] Parsing dev params for multi chains
[   5.0218 ] Generating br-bct
[   5.0221 ] Updating dev and MSS params in BR BCT
[   5.0221 ] tegrabct_v2 --dev_param tegra234-br-bct-p3701-0000_cpp.dtb --sdram tegra234-p3701-0000-sdram-l4t_cpp.dtb --brbct br_bct.cfg --chip 0x23 0
[   5.0823 ] Updating bl info
[   5.0826 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updateblinfo flash.xml.bin
[   5.1381 ] Generating br-bct
[   5.1384 ] Updating dev and MSS params in BR BCT
[   5.1384 ] tegrabct_v2 --dev_param tegra234-br-bct_b-p3701-0000_cpp.dtb --sdram tegra234-p3701-0000-sdram-l4t_cpp.dtb --brbct br_bct.cfg --chip 0x23 0
[   5.1999 ] Updating bl info
[   5.2003 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updateblinfo flash.xml.bin
[   5.2042 ] Generating signatures
[   5.2229 ] tegrasign_v3.py --key None --list images_list.xml --pubkeyhash pub_key.key --sha sha512
[   5.2231 ] Assuming zero filled SBK key
[   5.2238 ] Warning: pub_key.key is not found
[   5.2052 ] Parsing dev params for multi chains
[   5.2052 ] Generating br-bct
[   5.2054 ] Updating dev and MSS params in BR BCT
[   5.2054 ] tegrabct_v2 --dev_param tegra234-br-bct-p3701-0000_cpp.dtb --sdram tegra234-p3701-0000-sdram-l4t_cpp.dtb --brbct br_bct.cfg --chip 0x23 0
[   5.2659 ] Updating customer data section
[   5.2663 ] tegrabct_v2 --chip 0x23 0 --brbct br_bct_BR.bct --update_custinfo custinfo_out.bin
[   5.2844 ] Updating bl info
[   5.2848 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updateblinfo flash.xml.bin --updatesig images_list_signed.xml
[   5.2855 ] Generating SHA2 Hash
[   5.3048 ] Sha saved in br_bct_BR.sha
[   5.2861 ] Get Signed section of bct
[   5.2863 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --listbct bct_list.xml
[   5.2866 ] Signing BCT
[   5.3053 ] tegrasign_v3.py --key None --list bct_list.xml --pubkeyhash pub_key.key --sha sha512
[   5.3054 ] Assuming zero filled SBK key
[   5.3064 ] Sha saved in br_bct_BR.sha
[   5.3066 ] Warning: pub_key.key is not found
[   5.2879 ] Updating BCT with signature
[   5.2881 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updatesig bct_list_signed.xml
[   5.2882 ] Offset :4608 Len :3584
[   5.2888 ] Generating SHA2 Hash
[   5.3075 ] tegrasign_v3.py --key None --list bct_list.xml --sha sha512
[   5.3077 ] Assuming zero filled SBK key
[   5.3077 ] Assuming zero filled SBK key
[   5.3092 ] Sha saved in br_bct_BR.sha
[   5.2907 ] Updating BCT with SHA2 Hash
[   5.2910 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updatesha bct_list_signed.xml
[   5.2912 ] Offset :4608 Len :3584
[   5.2914 ] Offset :68 Len :8124
[   5.2917 ] Generating br-bct
[   5.2920 ] Updating dev and MSS params in BR BCT
[   5.2920 ] tegrabct_v2 --dev_param tegra234-br-bct_b-p3701-0000_cpp.dtb --sdram tegra234-p3701-0000-sdram-l4t_cpp.dtb --brbct br_bct.cfg --chip 0x23 0
[   5.3539 ] Updating customer data section
[   5.3544 ] tegrabct_v2 --chip 0x23 0 --brbct br_bct_BR.bct --update_custinfo custinfo_out.bin
[   5.3728 ] Updating bl info
[   5.3731 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updateblinfo flash.xml.bin --updatesig images_list_signed.xml
[   5.3977 ] Generating SHA2 Hash
[   5.4171 ] Sha saved in br_bct_BR.sha
[   5.3984 ] Get Signed section of bct
[   5.3986 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --listbct bct_list.xml
[   5.4214 ] Signing BCT
[   5.4402 ] tegrasign_v3.py --key None --list bct_list.xml --pubkeyhash pub_key.key --sha sha512
[   5.4403 ] Assuming zero filled SBK key
[   5.4417 ] Sha saved in br_bct_BR.sha
[   5.4418 ] Warning: pub_key.key is not found
[   5.4231 ] Updating BCT with signature
[   5.4233 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updatesig bct_list_signed.xml
[   5.4235 ] Offset :4608 Len :3584
[   5.4688 ] Generating SHA2 Hash
[   5.4875 ] tegrasign_v3.py --key None --list bct_list.xml --sha sha512
[   5.4876 ] Assuming zero filled SBK key
[   5.4877 ] Assuming zero filled SBK key
[   5.4892 ] Sha saved in br_bct_BR.sha
[   5.4707 ] Updating BCT with SHA2 Hash
[   5.4710 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updatesha bct_list_signed.xml
[   5.4713 ] Offset :4608 Len :3584
[   5.4715 ] Offset :68 Len :8124
[   5.4937 ] Generating coldboot mb1-bct
[   5.4941 ] tegrabct_v2 --chip 0x23 0 --mb1bct mb1_cold_boot_bct.cfg --misc tegra234-mb1-bct-misc-p3701-0000_cpp.dtb --wb0sdram tegra234-p3701-0000-wb0sdram-l4t_cpp.dtb --pinmux tegra234-mb1-bct-pinmux-p3701-0000-a04_cpp.dtb --pmc tegra234-mb1-bct-padvoltage-p3701-0000-a04_cpp.dtb --pmic tegra234-mb1-bct-pmic-p3701-0005_cpp.dtb --brcommand tegra234-mb1-bct-reset-p3701-0000_cpp.dtb --prod tegra234-mb1-bct-prod-p3701-0000_cpp.dtb --gpioint tegra234-mb1-bct-gpioint-p3701-0000_cpp.dtb --uphy tegra234-mb1-bct-uphylane-si_cpp.dtb --device tegra234-mb1-bct-device-p3701-0000_cpp.dtb --deviceprod tegra234-mb1-bct-cprod-p3701-0000_cpp.dtb --minratchet tegra234-mb1-bct-ratchet-p3701-0000_cpp.dtb --ratchet_blob ratchet_blob.bin
[   5.4944 ] MB1-BCT version: 0.13

[   5.4962 ] Parsing config file :tegra234-mb1-bct-pinmux-p3701-0000-a04_cpp.dtb 
[   5.4963 ] Added Platform Config 0 data with size :- 3320

[   5.4992 ] Parsing config file :tegra234-mb1-bct-padvoltage-p3701-0000-a04_cpp.dtb 
[   5.4993 ] WARNING: unknown node 'g2'
[   5.4993 ] WARNING: unknown node 'g2'
[   5.4994 ] WARNING: unknown node 'g9'
[   5.4994 ] WARNING: unknown node 'g9'
[   5.4995 ] Added Platform Config 2 data with size :- 24

[   5.4996 ] Parsing config file :tegra234-mb1-bct-pmic-p3701-0005_cpp.dtb 
[   5.4997 ] Added Platform Config 4 data with size :- 580
[   5.4997 ] 
[   5.4997 ] Parsing config file :tegra234-mb1-bct-reset-p3701-0000_cpp.dtb 
[   5.4997 ] Added Platform Config 3 data with size :- 52
[   5.4997 ] 
[   5.4997 ] Parsing config file :tegra234-mb1-bct-prod-p3701-0000_cpp.dtb 
[   5.4997 ] WARNING: unknown property 'major'
[   5.4997 ] WARNING: unknown property 'minor'
[   5.4997 ] Added Platform Config 5 data with size :- 524
[   5.4997 ] 
[   5.4997 ] Parsing config file :tegra234-mb1-bct-gpioint-p3701-0000_cpp.dtb 
[   5.4997 ] WARNING: unknown property 'major'
[   5.4997 ] WARNING: unknown property 'minor'
[   5.4997 ] Added Platform Config 7 data with size :- 380
[   5.4997 ] 
[   5.4997 ] Parsing config file :tegra234-mb1-bct-uphylane-si_cpp.dtb 
[   5.4997 ] Added Platform Config 8 data with size :- 24
[   5.4997 ] 
[   5.4997 ] Parsing config file :tegra234-mb1-bct-device-p3701-0000_cpp.dtb 
[   5.4997 ] Added Platform Config 9 data with size :- 100
[   5.4997 ] 
[   5.4997 ] Parsing config file :tegra234-mb1-bct-cprod-p3701-0000_cpp.dtb 
[   5.4997 ] ModuleCount 0 NumProdNames 0
[   5.4997 ] Added Platform Config 6 data with size :- 16
[   5.4997 ] 
[   5.4997 ] Parsing config file :tegra234-mb1-bct-ratchet-p3701-0000_cpp.dtb 
[   5.4997 ] 
[   5.4997 ] Updating mb1-bct with firmware information
[   5.5000 ] tegrabct_v2 --chip 0x23 0 --mb1bct mb1_cold_boot_bct_MB1.bct --updatefwinfo flash.xml.bin
[   5.5257 ] tegrahost_v2 --chip 0x23 0 --align mb1_cold_boot_bct_MB1_aligned.bct
[   5.5260 ] Generating SHA2 Hash for mb1bct
[   5.5452 ] Sha saved in mb1_cold_boot_bct_MB1_aligned.sha
[   5.5458 ] Sha saved in mb1_cold_boot_bct_MB1.sha
[   5.5272 ] tegrahost_v2 --chip 0x23 0 --magicid MBCT --ratchet_blob ratchet_blob.bin --appendsigheader mb1_cold_boot_bct_MB1_aligned.bct zerosbk
[   5.5274 ] adding BCH for mb1_cold_boot_bct_MB1_aligned.bct
[   5.5469 ] tegrasign_v3.py --key None --list mb1_cold_boot_bct_MB1_aligned_sigheader.bct_list.xml --pubkeyhash pub_key.key --sha sha512
[   5.5469 ] Assuming zero filled SBK key
[   5.5476 ] Warning: pub_key.key is not found
[   5.5291 ] tegrahost_v2 --chip 0x23 0 --updatesigheader mb1_cold_boot_bct_MB1_aligned_sigheader.bct.encrypt mb1_cold_boot_bct_MB1_aligned_sigheader.bct.hash zerosbk
[   5.5500 ] Generating recovery mb1-bct
[   5.5502 ] tegrabct_v2 --chip 0x23 0 --mb1bct mb1_bct.cfg --misc tegra234-mb1-bct-misc-p3701-0000_cpp.dtb --wb0sdram tegra234-p3701-0000-wb0sdram-l4t_cpp.dtb --pinmux tegra234-mb1-bct-pinmux-p3701-0000-a04_cpp.dtb --pmc tegra234-mb1-bct-padvoltage-p3701-0000-a04_cpp.dtb --pmic tegra234-mb1-bct-pmic-p3701-0005_cpp.dtb --brcommand tegra234-mb1-bct-reset-p3701-0000_cpp.dtb --prod tegra234-mb1-bct-prod-p3701-0000_cpp.dtb --gpioint tegra234-mb1-bct-gpioint-p3701-0000_cpp.dtb --uphy tegra234-mb1-bct-uphylane-si_cpp.dtb --device tegra234-mb1-bct-device-p3701-0000_cpp.dtb --deviceprod tegra234-mb1-bct-cprod-p3701-0000_cpp.dtb --minratchet tegra234-mb1-bct-ratchet-p3701-0000_cpp.dtb --ratchet_blob ratchet_blob.bin
[   5.5503 ] MB1-BCT version: 0.13

[   5.5522 ] Parsing config file :tegra234-mb1-bct-pinmux-p3701-0000-a04_cpp.dtb 
[   5.5523 ] Added Platform Config 0 data with size :- 3320

[   5.5552 ] Parsing config file :tegra234-mb1-bct-padvoltage-p3701-0000-a04_cpp.dtb 
[   5.5553 ] WARNING: unknown node 'g2'
[   5.5553 ] WARNING: unknown node 'g2'
[   5.5553 ] WARNING: unknown node 'g9'
[   5.5554 ] WARNING: unknown node 'g9'
[   5.5554 ] Added Platform Config 2 data with size :- 24

[   5.5554 ] Parsing config file :tegra234-mb1-bct-pmic-p3701-0005_cpp.dtb 
[   5.5555 ] Added Platform Config 4 data with size :- 580

[   5.5556 ] Parsing config file :tegra234-mb1-bct-reset-p3701-0000_cpp.dtb 
[   5.5557 ] Added Platform Config 3 data with size :- 52

[   5.5557 ] Parsing config file :tegra234-mb1-bct-prod-p3701-0000_cpp.dtb 
[   5.5558 ] WARNING: unknown property 'major'
[   5.5558 ] WARNING: unknown property 'minor'
[   5.5558 ] Added Platform Config 5 data with size :- 524
[   5.5558 ] 
[   5.5558 ] Parsing config file :tegra234-mb1-bct-gpioint-p3701-0000_cpp.dtb 
[   5.5558 ] WARNING: unknown property 'major'
[   5.5558 ] WARNING: unknown property 'minor'
[   5.5558 ] Added Platform Config 7 data with size :- 380
[   5.5558 ] 
[   5.5558 ] Parsing config file :tegra234-mb1-bct-uphylane-si_cpp.dtb 
[   5.5558 ] Added Platform Config 8 data with size :- 24
[   5.5558 ] 
[   5.5558 ] Parsing config file :tegra234-mb1-bct-device-p3701-0000_cpp.dtb 
[   5.5558 ] Added Platform Config 9 data with size :- 100
[   5.5558 ] 
[   5.5558 ] Parsing config file :tegra234-mb1-bct-cprod-p3701-0000_cpp.dtb 
[   5.5558 ] ModuleCount 0 NumProdNames 0
[   5.5558 ] Added Platform Config 6 data with size :- 16
[   5.5558 ] 
[   5.5558 ] Parsing config file :tegra234-mb1-bct-ratchet-p3701-0000_cpp.dtb 
[   5.5558 ] 
[   5.5558 ] Updating mb1-bct with firmware information
[   5.5560 ] tegrabct_v2 --chip 0x23 0 --mb1bct mb1_bct_MB1.bct --recov --updatefwinfo flash.xml.bin
[   5.5779 ] tegrahost_v2 --chip 0x23 0 --align mb1_bct_MB1_aligned.bct
[   5.5781 ] Generating SHA2 Hash for mb1bct
[   5.5974 ] Sha saved in mb1_bct_MB1_aligned.sha
[   5.5979 ] Sha saved in mb1_bct_MB1.sha
[   5.5793 ] tegrahost_v2 --chip 0x23 0 --magicid MBCT --ratchet_blob ratchet_blob.bin --appendsigheader mb1_bct_MB1_aligned.bct zerosbk
[   5.5795 ] adding BCH for mb1_bct_MB1_aligned.bct
[   5.5989 ] tegrasign_v3.py --key None --list mb1_bct_MB1_aligned_sigheader.bct_list.xml --pubkeyhash pub_key.key --sha sha512
[   5.5990 ] Assuming zero filled SBK key
[   5.5999 ] Warning: pub_key.key is not found
[   5.5815 ] tegrahost_v2 --chip 0x23 0 --updatesigheader mb1_bct_MB1_aligned_sigheader.bct.encrypt mb1_bct_MB1_aligned_sigheader.bct.hash zerosbk
[   5.5822 ] Generating coldboot mem-bct
[   5.5825 ] tegrabct_v2 --chip 0x23 0 --sdram tegra234-p3701-0000-sdram-l4t_cpp.dtb --wb0sdram tegra234-p3701-0000-wb0sdram-l4t_cpp.dtb --membct tegra234-p3701-0000-sdram-l4t_cpp_1.bct tegra234-p3701-0000-sdram-l4t_cpp_2.bct tegra234-p3701-0000-sdram-l4t_cpp_3.bct tegra234-p3701-0000-sdram-l4t_cpp_4.bct
[   5.5827 ]  packing sdram params with Wb0 file tegra234-p3701-0000-wb0sdram-l4t_cpp.dtb
[   5.6422 ] Packing sdram param for instance[0]
[   5.6423 ] Packing sdram param for instance[1]
[   5.6423 ] Packing sdram param for instance[2]
[   5.6424 ] Packing sdram param for instance[3]
[   5.6424 ] Packing sdram param for instance[4]
[   5.6424 ] Packing sdram param for instance[5]
[   5.6425 ] Packing sdram param for instance[6]
[   5.6425 ] Packing sdram param for instance[7]
[   5.6426 ] Packing sdram param for instance[8]
[   5.6426 ] Packing sdram param for instance[9]
[   5.6427 ] Packing sdram param for instance[10]
[   5.6427 ] Packing sdram param for instance[11]
[   5.6428 ] Packing sdram param for instance[12]
[   5.6428 ] Packing sdram param for instance[13]
[   5.6428 ] Packing sdram param for instance[14]
[   5.6429 ] Packing sdram param for instance[15]
[   5.7039 ] Getting sector size from pt
[   5.7043 ] tegraparser_v2 --getsectorsize flash.xml.bin sector_info.bin
[   5.7047 ] BlockSize read from layout is 0x200

[   5.7048 ] tegrahost_v2 --chip 0x23 0 --blocksize 512 --magicid MEMB --addsigheader_multi tegra234-p3701-0000-sdram-l4t_cpp_1.bct tegra234-p3701-0000-sdram-l4t_cpp_2.bct tegra234-p3701-0000-sdram-l4t_cpp_3.bct tegra234-p3701-0000-sdram-l4t_cpp_4.bct
[   5.7049 ] Binary 0 length is 58752
[   5.7052 ] Binary 0 align length is 58880
[   5.7058 ] Binary 1 length is 58752
[   5.7059 ] Binary 1 align length is 58880
[   5.7062 ] Binary 2 length is 58752
[   5.7062 ] Binary 2 align length is 58880
[   5.7066 ] Binary 3 length is 58752
[   5.7067 ] Binary 3 align length is 58880
[   5.7070 ] Buffer length is 235520
[   5.7070 ] adding BCH for tegra234-p3701-0000-sdram-l4t_cpp_1.bct
[   5.7071 ] new length is 243712
[   5.7077 ] tegrahost_v2 --chip 0x23 0 --align mem_coldboot_aligned.bct
[   5.7082 ] tegrahost_v2 --chip 0x23 0 --magicid MEMB --ratchet_blob ratchet_blob.bin --appendsigheader mem_coldboot_aligned.bct zerosbk
[   5.7083 ] Header already present for mem_coldboot_aligned.bct
[   5.7277 ] tegrasign_v3.py --key None --list mem_coldboot_aligned_sigheader.bct_list.xml --pubkeyhash pub_key.key --sha sha512
[   5.7279 ] Assuming zero filled SBK key
[   5.7291 ] Warning: pub_key.key is not found
[   5.7107 ] tegrahost_v2 --chip 0x23 0 --updatesigheader mem_coldboot_aligned_sigheader.bct.encrypt mem_coldboot_aligned_sigheader.bct.hash zerosbk
[   5.7118 ] Generating recovery mem-bct
[   5.7121 ] tegrabct_v2 --chip 0x23 0 --sdram tegra234-p3701-0000-sdram-l4t_cpp.dtb --wb0sdram tegra234-p3701-0000-wb0sdram-l4t_cpp.dtb --membct tegra234-p3701-0000-sdram-l4t_cpp_1.bct tegra234-p3701-0000-sdram-l4t_cpp_2.bct tegra234-p3701-0000-sdram-l4t_cpp_3.bct tegra234-p3701-0000-sdram-l4t_cpp_4.bct
[   5.7122 ]  packing sdram params with Wb0 file tegra234-p3701-0000-wb0sdram-l4t_cpp.dtb
[   5.7749 ] Packing sdram param for instance[0]
[   5.7749 ] Packing sdram param for instance[1]
[   5.7750 ] Packing sdram param for instance[2]
[   5.7750 ] Packing sdram param for instance[3]
[   5.7751 ] Packing sdram param for instance[4]
[   5.7751 ] Packing sdram param for instance[5]
[   5.7751 ] Packing sdram param for instance[6]
[   5.7752 ] Packing sdram param for instance[7]
[   5.7752 ] Packing sdram param for instance[8]
[   5.7753 ] Packing sdram param for instance[9]
[   5.7753 ] Packing sdram param for instance[10]
[   5.7753 ] Packing sdram param for instance[11]
[   5.7754 ] Packing sdram param for instance[12]
[   5.7754 ] Packing sdram param for instance[13]
[   5.7755 ] Packing sdram param for instance[14]
[   5.7755 ] Packing sdram param for instance[15]
[   5.8352 ] Reading ramcode from backup chip_info.bin file
[   5.8613 ] RAMCODE Read from Device: 0

[   5.8613 ] Using ramcode 0
[   5.8613 ] Disabled BPMP dtb trim, using default dtb
[   5.8613 ] 
[   5.8618 ] tegrahost_v2 --chip 0x23 0 --align mem_rcm_aligned.bct
[   5.8623 ] tegrahost_v2 --chip 0x23 0 --magicid MEM0 --ratchet_blob ratchet_blob.bin --appendsigheader mem_rcm_aligned.bct zerosbk
[   5.8625 ] adding BCH for mem_rcm_aligned.bct
[   5.8831 ] tegrasign_v3.py --key None --list mem_rcm_aligned_sigheader.bct_list.xml --pubkeyhash pub_key.key --sha sha512
[   5.8833 ] Assuming zero filled SBK key
[   5.8844 ] Warning: pub_key.key is not found
[   5.8660 ] tegrahost_v2 --chip 0x23 0 --updatesigheader mem_rcm_aligned_sigheader.bct.encrypt mem_rcm_aligned_sigheader.bct.hash zerosbk
[   5.8668 ] Copying signatures
[   5.8671 ] tegrahost_v2 --chip 0x23 0 --partitionlayout flash.xml.bin --updatesig images_list_signed.xml
[   5.8678 ] tegraparser_v2 --generategpt --pt flash.xml.bin
[   5.8680 ] gpt_primary_9_0.bin:
[   5.8682 ] partition_id	partition_name			      StartingLba	EndingLba
[   5.8684 ]            1	APP                                 	 3050048119537623
[   5.8686 ]            2	A_kernel                            	      40  262183
[   5.8688 ]            3	A_kernel-dtb                        	  262184  263719
[   5.8689 ]            4	A_reserved_on_user                  	  263720  328487
[   5.8691 ]            5	B_kernel                            	  328488  590631
[   5.8693 ]            6	B_kernel-dtb                        	  590632  592167
[   5.8695 ]            7	B_reserved_on_user                  	  592168  656935
[   5.8696 ]            8	recovery                            	  656936  820775
[   5.8698 ]            9	recovery-dtb                        	  820776  821799
[   5.8700 ]           10	esp                                 	  821800  952871
[   5.8702 ]           11	recovery_alt                        	  952872 1116711
[   5.8704 ]           12	recovery-dtb_alt                    	 1116712 1117735
[   5.8706 ]           13	esp_alt                             	 1117736 1248807
[   5.8707 ]           14	UDA                                 	 1248832 2068031
[   5.8710 ]           15	reserved                            	 2068032 3050047
[   5.8711 ] gpt_secondary_9_0.bin:
[   5.8711 ] partition_id	partition_name			      StartingLba	EndingLba
[   5.8712 ]            1	APP                                 	 3050048119537623
[   5.8712 ]            2	A_kernel                            	      40  262183
[   5.8713 ]            3	A_kernel-dtb                        	  262184  263719
[   5.8714 ]            4	A_reserved_on_user                  	  263720  328487
[   5.8715 ]            5	B_kernel                            	  328488  590631
[   5.8715 ]            6	B_kernel-dtb                        	  590632  592167
[   5.8716 ]            7	B_reserved_on_user                  	  592168  656935
[   5.8717 ]            8	recovery                            	  656936  820775
[   5.8718 ]            9	recovery-dtb                        	  820776  821799
[   5.8719 ]           10	esp                                 	  821800  952871
[   5.8720 ]           11	recovery_alt                        	  952872 1116711
[   5.8721 ]           12	recovery-dtb_alt                    	 1116712 1117735
[   5.8721 ]           13	esp_alt                             	 1117736 1248807
[   5.8722 ]           14	UDA                                 	 1248832 2068031
[   5.8723 ]           15	reserved                            	 2068032 3050047
[   5.9807 ] tegrahost_v2 --chip 0x23 0 --align uefi_jetson_with_dtb_aligned.bin
[   5.9812 ] tegrahost_v2 --chip 0x23 0 --magicid CPBL --ratchet_blob ratchet_blob.bin --appendsigheader uefi_jetson_with_dtb_aligned.bin zerosbk
[   5.9814 ] adding BCH for uefi_jetson_with_dtb_aligned.bin
[   6.0517 ] tegrasign_v3.py --key None --list uefi_jetson_with_dtb_aligned_sigheader.bin_list.xml --pubkeyhash pub_key.key --sha sha512
[   6.0518 ] Assuming zero filled SBK key
[   6.0571 ] Warning: pub_key.key is not found
[   6.0387 ] tegrahost_v2 --chip 0x23 0 --updatesigheader uefi_jetson_with_dtb_aligned_sigheader.bin.encrypt uefi_jetson_with_dtb_aligned_sigheader.bin.hash zerosbk
[   6.0972 ] Copying enc\/signed file in /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   6.0973 ] Copying br bct for multi chains
[   6.0974 ] Signed BCT for boot chain A is copied to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/br_bct_BR.bct

[   6.0975 ] Signed BCT for boot chain B is copied to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/br_bct_b_BR.bct

[   6.0981 ] Copying uefi_jetson_with_dtb_sigheader.bin.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   6.0995 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/uefi_jetson_with_dtb_sigheader.bin.encrypt
[   6.1009 ] tegraparser_v2 --pt flash.xml.bin --generateflashindex /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/flash.xml.tmp flash.idx
Using bpmp-dtb concatenated with odmdata in blob for t23x
./tegraflash.py --bl uefi_jetson_with_dtb_sigheader.bin.encrypt --bct br_bct_BR.bct --bldtb tegra234-p3737-0000+p3701-0004-nv.dtb --applet rcm_2_encrypt.rcm --applet_softfuse rcm_1_encrypt.rcm --cmd "secureflash;reboot"  --cfg secureflash.xml --chip 0x23 --mb1_bct mb1_bct_MB1_sigheader.bct.encrypt --mem_bct mem_rcm_sigheader.bct.encrypt --mb1_cold_boot_bct mb1_cold_boot_bct_MB1_sigheader.bct.encrypt --mb1_bin mb1_t234_prod_aligned_sigheader.bin.encrypt --psc_bl1_bin psc_bl1_t234_prod_aligned_sigheader.bin.encrypt --mem_bct_cold_boot mem_coldboot_sigheader.bct.encrypt  --bins "psc_fw pscfw_t234_prod_sigheader.bin.encrypt; mts_mce mce_flash_o10_cr_prod_sigheader.bin.encrypt; tsec_fw tsec_t234_sigheader.bin.encrypt; mb2_applet applet_t234_sigheader.bin.encrypt; mb2_bootloader mb2_t234_with_mb2_bct_MB2_sigheader.bin.encrypt; xusb_fw xusb_t234_prod_sigheader.bin.encrypt; pva_fw nvpva_020_sigheader.fw.encrypt; dce_fw display-t234-dce_sigheader.bin.encrypt; nvdec nvdec_t234_prod_sigheader.fw.encrypt; bpmp_fw bpmp_t234-TE990M-A1_prod_sigheader.bin.encrypt; bpmp_fw_dtb tegra234-bpmp-3701-0004-3737-0000_with_odm_sigheader.dtb.encrypt; rce_fw camera-rtcpu-t234-rce_sigheader.img.encrypt; ape_fw adsp-fw_sigheader.bin.encrypt; spe_fw spe_t234_sigheader.bin.encrypt; tos tos-optee_t234_sigheader.img.encrypt; eks eks_t234_sigheader.img.encrypt"   
saving flash command in flashcmd.txt

*** no-flash flag enabled. Exiting now... *** 

User can run above saved command in factory environment without 
providing pkc and sbk keys to flash a device

Example:

    $ cd bootloader 
    $ sudo bash ./flashcmd.txt

'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/flash.idx' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/external/flash.idx'
Flash index file is /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/flash.idx
Number of lines is 18
max_index=17
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/mbr_9_0.bin  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/external/mbr_9_0.bin
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/mbr_9_0.bin' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/external/mbr_9_0.bin'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/gpt_primary_9_0.bin  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/external/gpt_primary_9_0.bin
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/gpt_primary_9_0.bin' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/external/gpt_primary_9_0.bin'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/boot.img  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/external/boot.img
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/boot.img' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/external/boot.img'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/kernel_tegra234-p3737-0000+p3701-0004-nv.dtb  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/external/kernel_tegra234-p3737-0000+p3701-0004-nv.dtb
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/kernel_tegra234-p3737-0000+p3701-0004-nv.dtb' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/external/kernel_tegra234-p3737-0000+p3701-0004-nv.dtb'
Warning: skip writing A_reserved_on_user partition as no image is specified
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/boot.img  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/external/boot.img
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/boot.img' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/external/boot.img'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/kernel_tegra234-p3737-0000+p3701-0004-nv.dtb  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/external/kernel_tegra234-p3737-0000+p3701-0004-nv.dtb
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/kernel_tegra234-p3737-0000+p3701-0004-nv.dtb' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/external/kernel_tegra234-p3737-0000+p3701-0004-nv.dtb'
Warning: skip writing B_reserved_on_user partition as no image is specified
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/recovery.img  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/external/recovery.img
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/recovery.img' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/external/recovery.img'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/tegra234-p3737-0000+p3701-0004-nv.dtb.rec  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/external/tegra234-p3737-0000+p3701-0004-nv.dtb.rec
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/tegra234-p3737-0000+p3701-0004-nv.dtb.rec' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/external/tegra234-p3737-0000+p3701-0004-nv.dtb.rec'
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/esp.img  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/external/esp.img
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/esp.img' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/external/esp.img'
Warning: skip writing recovery_alt partition as no image is specified
Warning: skip writing recovery-dtb_alt partition as no image is specified
Warning: skip writing esp_alt partition as no image is specified
XPath set is empty
No image is found for UDA partition
Warning: skip writing reserved partition as no image is specified
Copying APP image into  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/external/system.img
tar: Write checkpoint 10000
tar: Write checkpoint 20000
tar: Write checkpoint 30000
tar: Write checkpoint 40000
tar: Write checkpoint 50000
tar: Write checkpoint 60000
tar: Write checkpoint 70000
tar: Write checkpoint 80000
tar: Write checkpoint 90000
tar: Write checkpoint 100000
tar: Write checkpoint 110000
tar: Write checkpoint 120000
tar: Write checkpoint 130000
tar: Write checkpoint 140000
tar: Write checkpoint 150000
tar: Write checkpoint 160000
tar: Write checkpoint 170000
tar: Write checkpoint 180000
tar: Write checkpoint 190000
tar: Write checkpoint 200000
tar: Write checkpoint 210000
tar: Write checkpoint 220000
tar: Write checkpoint 230000
tar: Write checkpoint 240000
tar: Write checkpoint 250000
tar: Write checkpoint 260000
tar: Write checkpoint 270000
tar: Write checkpoint 280000
tar: Write checkpoint 290000
tar: Write checkpoint 300000
tar: Write checkpoint 310000
tar: Write checkpoint 320000
tar: Write checkpoint 330000
tar: Write checkpoint 340000
tar: Write checkpoint 350000
tar: Write checkpoint 360000
tar: Write checkpoint 370000
tar: Write checkpoint 380000
tar: Write checkpoint 390000
tar: Write checkpoint 400000
tar: Write checkpoint 410000
tar: Write checkpoint 420000
tar: Write checkpoint 430000
tar: Write checkpoint 440000
tar: Write checkpoint 450000
tar: Write checkpoint 460000
tar: Write checkpoint 470000
tar: Write checkpoint 480000
tar: Write checkpoint 490000
tar: Write checkpoint 500000
tar: Write checkpoint 510000
tar: Write checkpoint 520000
tar: Write checkpoint 530000
tar: Write checkpoint 540000
tar: Write checkpoint 550000
tar: Write checkpoint 560000
tar: Write checkpoint 570000
tar: Write checkpoint 580000
tar: Write checkpoint 590000
tar: Write checkpoint 600000
tar: Write checkpoint 610000
tar: Write checkpoint 620000
tar: Write checkpoint 630000
tar: Write checkpoint 640000
tar: Write checkpoint 650000
tar: Write checkpoint 660000
tar: Write checkpoint 670000
tar: Write checkpoint 680000
tar: Write checkpoint 690000
tar: Write checkpoint 700000
tar: Write checkpoint 710000
tar: Write checkpoint 720000
tar: Write checkpoint 730000
tar: Write checkpoint 740000
tar: Write checkpoint 750000
tar: Write checkpoint 760000
tar: Write checkpoint 770000
tar: Write checkpoint 780000
tar: Write checkpoint 790000
tar: Write checkpoint 800000
tar: Write checkpoint 810000
tar: Write checkpoint 820000
tar: Write checkpoint 830000
tar: Write checkpoint 840000
tar: Write checkpoint 850000
tar: Write checkpoint 860000
tar: Write checkpoint 870000
tar: Write checkpoint 880000
tar: Write checkpoint 890000
tar: Write checkpoint 900000
tar: Write checkpoint 910000
tar: Write checkpoint 920000
tar: Write checkpoint 930000
tar: Write checkpoint 940000
tar: Write checkpoint 950000
tar: Write checkpoint 960000
tar: Write checkpoint 970000
tar: Write checkpoint 980000
tar: Write checkpoint 990000
tar: Write checkpoint 1000000
tar: Write checkpoint 1010000
tar: Write checkpoint 1020000
tar: Write checkpoint 1030000
tar: Write checkpoint 1040000
tar: Write checkpoint 1050000
tar: Write checkpoint 1060000
tar: Write checkpoint 1070000
tar: Write checkpoint 1080000
tar: Write checkpoint 1090000
tar: Write checkpoint 1100000
tar: Write checkpoint 1110000
tar: Write checkpoint 1120000
tar: Write checkpoint 1130000
tar: Write checkpoint 1140000
tar: Write checkpoint 1150000
tar: Write checkpoint 1160000
tar: Write checkpoint 1170000
tar: Write checkpoint 1180000
tar: Write checkpoint 1190000
tar: Write checkpoint 1200000
tar: Write checkpoint 1210000
tar: Write checkpoint 1220000
tar: Write checkpoint 1230000
tar: Write checkpoint 1240000
tar: Write checkpoint 1250000
tar: Write checkpoint 1260000
tar: Write checkpoint 1270000
tar: Write checkpoint 1280000
tar: Write checkpoint 1290000
tar: Write checkpoint 1300000
tar: Write checkpoint 1310000
tar: Write checkpoint 1320000
tar: Write checkpoint 1330000
tar: Write checkpoint 1340000
tar: Write checkpoint 1350000
tar: Write checkpoint 1360000
tar: Write checkpoint 1370000
tar: Write checkpoint 1380000
tar: Write checkpoint 1390000
tar: Write checkpoint 1400000
tar: Write checkpoint 1410000
tar: Write checkpoint 1420000
tar: Write checkpoint 1430000
tar: Write checkpoint 1440000
tar: Write checkpoint 1450000
tar: Write checkpoint 1460000
tar: Write checkpoint 1470000
tar: Write checkpoint 1480000
tar: Write checkpoint 1490000
tar: Write checkpoint 1500000
tar: Write checkpoint 1510000
tar: Write checkpoint 1520000
tar: Write checkpoint 1530000
tar: Write checkpoint 1540000
tar: Write checkpoint 1550000
tar: Write checkpoint 1560000
tar: Write checkpoint 1570000
tar: Write checkpoint 1580000
tar: Write checkpoint 1590000
tar: Write checkpoint 1600000
tar: Write checkpoint 1610000
tar: Write checkpoint 1620000
tar: Write checkpoint 1630000
tar: Write checkpoint 1640000
tar: Write checkpoint 1650000
tar: Write checkpoint 1660000
tar: Write checkpoint 1670000
tar: Write checkpoint 1680000
tar: Write checkpoint 1690000
tar: Write checkpoint 1700000
tar: Write checkpoint 1710000
tar: Write checkpoint 1720000
tar: Write checkpoint 1730000
tar: Write checkpoint 1740000
tar: Write checkpoint 1750000
tar: Write checkpoint 1760000
tar: Write checkpoint 1770000
tar: Write checkpoint 1780000
tar: Write checkpoint 1790000
tar: Write checkpoint 1800000
tar: Write checkpoint 1810000
tar: Write checkpoint 1820000
tar: Write checkpoint 1830000
tar: Write checkpoint 1840000
tar: Write checkpoint 1850000
tar: Write checkpoint 1860000
tar: Write checkpoint 1870000
tar: Write checkpoint 1880000
tar: Write checkpoint 1890000
tar: Write checkpoint 1900000
tar: Write checkpoint 1910000
tar: Write checkpoint 1920000
tar: Write checkpoint 1930000
tar: Write checkpoint 1940000
tar: Write checkpoint 1950000
tar: Write checkpoint 1960000
tar: Write checkpoint 1970000
tar: Write checkpoint 1980000
tar: Write checkpoint 1990000
tar: Write checkpoint 2000000
tar: Write checkpoint 2010000
tar: Write checkpoint 2020000
tar: Write checkpoint 2030000
tar: Write checkpoint 2040000
tar: Write checkpoint 2050000
tar: Write checkpoint 2060000
tar: Write checkpoint 2070000
tar: Write checkpoint 2080000
tar: Write checkpoint 2090000
tar: Write checkpoint 2100000
tar: Write checkpoint 2110000
tar: Write checkpoint 2120000
tar: Write checkpoint 2130000
tar: Write checkpoint 2140000
tar: Write checkpoint 2150000
tar: Write checkpoint 2160000
tar: Write checkpoint 2170000
tar: Write checkpoint 2180000
tar: Write checkpoint 2190000
tar: Write checkpoint 2200000
tar: Write checkpoint 2210000
tar: Write checkpoint 2220000
tar: Write checkpoint 2230000
tar: Write checkpoint 2240000
tar: Write checkpoint 2250000
tar: Write checkpoint 2260000
tar: Write checkpoint 2270000
tar: Write checkpoint 2280000
tar: Write checkpoint 2290000
tar: Write checkpoint 2300000
tar: Write checkpoint 2310000
tar: Write checkpoint 2320000
tar: Write checkpoint 2330000
tar: Write checkpoint 2340000
tar: Write checkpoint 2350000
tar: Write checkpoint 2360000
tar: Write checkpoint 2370000
tar: Write checkpoint 2380000
tar: Write checkpoint 2390000
tar: Write checkpoint 2400000
tar: Write checkpoint 2410000
tar: Write checkpoint 2420000
tar: Write checkpoint 2430000
tar: Write checkpoint 2440000
tar: Write checkpoint 2450000
tar: Write checkpoint 2460000
tar: Write checkpoint 2470000
tar: Write checkpoint 2480000
tar: Write checkpoint 2490000
tar: Write checkpoint 2500000
tar: Write checkpoint 2510000
tar: Write checkpoint 2520000
tar: Write checkpoint 2530000
tar: Write checkpoint 2540000
tar: Write checkpoint 2550000
tar: Write checkpoint 2560000
tar: Write checkpoint 2570000
tar: Write checkpoint 2580000
tar: Write checkpoint 2590000
tar: Write checkpoint 2600000
tar: Write checkpoint 2610000
tar: Write checkpoint 2620000
tar: Write checkpoint 2630000
tar: Write checkpoint 2640000
tar: Write checkpoint 2650000
tar: Write checkpoint 2660000
tar: Write checkpoint 2670000
tar: Write checkpoint 2680000
tar: Write checkpoint 2690000
tar: Write checkpoint 2700000
tar: Write checkpoint 2710000
tar: Write checkpoint 2720000
tar: Write checkpoint 2730000
tar: Write checkpoint 2740000
tar: Write checkpoint 2750000
tar: Write checkpoint 2760000
tar: Write checkpoint 2770000
tar: Write checkpoint 2780000
tar: Write checkpoint 2790000
tar: Write checkpoint 2800000
tar: Write checkpoint 2810000
tar: Write checkpoint 2820000
tar: Write checkpoint 2830000
tar: Write checkpoint 2840000
tar: Write checkpoint 2850000
tar: Write checkpoint 2860000
tar: Write checkpoint 2870000
tar: Write checkpoint 2880000
tar: Write checkpoint 2890000
tar: Write checkpoint 2900000
tar: Write checkpoint 2910000
tar: Write checkpoint 2920000
tar: Write checkpoint 2930000
tar: Write checkpoint 2940000
tar: Write checkpoint 2950000
tar: Write checkpoint 2960000
tar: Write checkpoint 2970000
tar: Write checkpoint 2980000
tar: Write checkpoint 2990000
tar: Write checkpoint 3000000
tar: Write checkpoint 3010000
tar: Write checkpoint 3020000
tar: Write checkpoint 3030000
tar: Write checkpoint 3040000
tar: Write checkpoint 3050000
tar: Write checkpoint 3060000
tar: Write checkpoint 3070000
tar: Write checkpoint 3080000
tar: Write checkpoint 3090000
tar: Write checkpoint 3100000
tar: Write checkpoint 3110000
tar: Write checkpoint 3120000
tar: Write checkpoint 3130000
tar: Write checkpoint 3140000
tar: Write checkpoint 3150000
tar: Write checkpoint 3160000
tar: Write checkpoint 3170000
tar: Write checkpoint 3180000
tar: Write checkpoint 3190000
tar: Write checkpoint 3200000
Copying /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/gpt_secondary_9_0.bin  /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/external/gpt_secondary_9_0.bin
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/gpt_secondary_9_0.bin' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/external/gpt_secondary_9_0.bin'
Copy flash script to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images
'/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/l4t_flash_from_kernel.sh' -> '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/images/l4t_flash_from_kernel.sh'
Success
******************************************
*                                        *
*  Step 2: Generate rcm boot commandline *
*                                        *
******************************************
ROOTFS_AB= ROOTFS_ENC= /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/flash.sh  --no-flash --rcm-boot jetson-agx-orin-devkit mmcblk0p1
###############################################################################
# L4T BSP Information:
# R36 , REVISION: 3.0
# User release: 0.0
###############################################################################
ECID is 0x80012344705DF1172C0000000D020080
Existing emcfuse(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/fuse_t234.xml) reused.
copying emc_fuse_dev_params(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-br-bct-diag-boot.dts)... done.
copying device_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-device-p3701-0000.dts)... done.
copying misc_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-misc-p3701-0000.dts)... done.
./tegraflash.py --chip "0x23" --applet "/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/mb1_t234_prod.bin" --skipuid --cfg readinfo_t234_min_prod.xml --dev_params tegra234-br-bct-diag-boot.dts --device_config tegra234-mb1-bct-device-p3701-0000.dts --misc_config tegra234-mb1-bct-misc-p3701-0000.dts --bins "mb2_applet applet_t234.bin" --cmd "readfuses fuse_t234.bin fuse_t234.xml; dump eeprom cvm cvm.bin; dump try_custinfo custinfo_out.bin; reboot recovery" 
Welcome to Tegra Flash
version 1.0.0
Type ? or help for help and q or quit to exit
Use ! to execute system commands
 
[   0.0667 ] Reading fuses
[   0.0671 ] tegrarcm_v2 --chip 0x23 0 --ismb2applet
[   0.0673 ] File rcm_state open failed
[   0.0675 ] ERROR: failed to read rcm_state
[   0.0675 ] 
[   0.0963 ] tegrasign_v3.py --key None --getmode mode.txt
[   0.0964 ] Assuming zero filled SBK key
[   0.0677 ] Pre-processing config: tegra234-mb1-bct-device-p3701-0000.dts
[   0.2437 ] Pre-processing config: tegra234-mb1-bct-misc-p3701-0000.dts
[   0.2640 ] Parsing partition layout
[   0.2725 ] tegraparser_v2 --pt readinfo_t234_min_prod.xml.tmp
[   0.2757 ] Kernel DTB used: None
[   0.2757 ] WARNING: dce base dtb is not provided

[   0.2757 ] Parsing partition layout
[   0.2761 ] tegraparser_v2 --pt readinfo_t234_min_prod.xml.tmp
[   0.2766 ] Creating list of images to be signed
[   0.2881 ] tegrahost_v2 --chip 0x23 0 --partitionlayout readinfo_t234_min_prod.xml.bin --list images_list.xml zerosbk
[   0.2883 ] MB1: Nvheader already present is mb1_t234_prod_aligned.bin
[   0.3079 ] Header already present for mb1_t234_prod_aligned_sigheader.bin
[   0.3082 ] MB1: Nvheader already present is mb1_t234_prod_aligned.bin
[   0.3118 ] Header already present for mb1_t234_prod_aligned_sigheader.bin
[   0.3127 ] MB1: Nvheader already present is psc_bl1_t234_prod_aligned.bin
[   0.3268 ] Header already present for psc_bl1_t234_prod_aligned_sigheader.bin
[   0.3271 ] adding BCH for mb2_t234_aligned.bin
[   0.3430 ] MB1: Nvheader already present is psc_bl1_t234_prod_aligned.bin
[   0.3489 ] Header already present for psc_bl1_t234_prod_aligned_sigheader.bin
[   0.3491 ] adding BCH for mb2_t234_aligned.bin
[   0.3564 ] Filling MB1 storage info
[   0.3564 ] Parsing dev params for multi chains
[   0.3607 ] Generating br-bct
[   0.3713 ] Updating dev and MSS params in BR BCT
[   0.3713 ] tegrabct_v2 --dev_param tegra234-br-bct-diag-boot_cpp.dtb --brbct br_bct.cfg --chip 0x23 0
[   0.3759 ] Updating bl info
[   0.3762 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updateblinfo readinfo_t234_min_prod.xml.bin
[   0.3763 ] WARNING: boot chain is not completed. set to 0
[   0.3769 ] Generating signatures
[   0.4058 ] tegrasign_v3.py --key None --list images_list.xml --pubkeyhash pub_key.key --sha sha512
[   0.4058 ] Assuming zero filled SBK key
[   0.4882 ] Warning: pub_key.key is not found
[   0.4595 ] Parsing dev params for multi chains
[   0.4595 ] Generating br-bct
[   0.4596 ] Updating dev and MSS params in BR BCT
[   0.4597 ] tegrabct_v2 --dev_param tegra234-br-bct-diag-boot_cpp.dtb --brbct br_bct.cfg --chip 0x23 0
[   0.4601 ] Updating bl info
[   0.4602 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updateblinfo readinfo_t234_min_prod.xml.bin --updatesig images_list_signed.xml
[   0.4604 ] WARNING: boot chain is not completed. set to 0
[   0.4617 ] Generating SHA2 Hash
[   0.4910 ] Sha saved in br_bct_BR.sha
[   0.4622 ] Get Signed section of bct
[   0.4624 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --listbct bct_list.xml
[   0.4627 ] Signing BCT
[   0.4916 ] tegrasign_v3.py --key None --list bct_list.xml --pubkeyhash pub_key.key --sha sha512
[   0.4916 ] Assuming zero filled SBK key
[   0.4927 ] Sha saved in br_bct_BR.sha
[   0.4928 ] Warning: pub_key.key is not found
[   0.4640 ] Updating BCT with signature
[   0.4642 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updatesig bct_list_signed.xml
[   0.4643 ] Offset :4608 Len :3584
[   0.4649 ] Generating SHA2 Hash
[   0.4937 ] tegrasign_v3.py --key None --list bct_list.xml --sha sha512
[   0.4939 ] Assuming zero filled SBK key
[   0.4939 ] Assuming zero filled SBK key
[   0.4954 ] Sha saved in br_bct_BR.sha
[   0.4668 ] Updating BCT with SHA2 Hash
[   0.4671 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updatesha bct_list_signed.xml
[   0.4673 ] Offset :4608 Len :3584
[   0.4676 ] Offset :68 Len :8124
[   0.4678 ] Generating coldboot mb1-bct
[   0.4681 ] tegrabct_v2 --chip 0x23 0 --mb1bct mb1_cold_boot_bct.cfg --misc tegra234-mb1-bct-misc-p3701-0000_cpp.dtb --device tegra234-mb1-bct-device-p3701-0000_cpp.dtb
[   0.4683 ] MB1-BCT version: 0.13

[   0.4697 ] Parsing config file :tegra234-mb1-bct-device-p3701-0000_cpp.dtb 
[   0.4698 ] Added Platform Config 9 data with size :- 100
[   0.4699 ] 
[   0.4699 ] Updating mb1-bct with firmware information
[   0.4702 ] tegrabct_v2 --chip 0x23 0 --mb1bct mb1_cold_boot_bct_MB1.bct --updatefwinfo readinfo_t234_min_prod.xml.bin
[   0.4711 ] tegrahost_v2 --chip 0x23 0 --align mb1_cold_boot_bct_MB1_aligned.bct
[   0.4714 ] Generating SHA2 Hash for mb1bct
[   0.5006 ] Sha saved in mb1_cold_boot_bct_MB1_aligned.sha
[   0.5011 ] Sha saved in mb1_cold_boot_bct_MB1.sha
[   0.4724 ] tegrahost_v2 --chip 0x23 0 --magicid MBCT --appendsigheader mb1_cold_boot_bct_MB1_aligned.bct zerosbk
[   0.4726 ] adding BCH for mb1_cold_boot_bct_MB1_aligned.bct
[   0.5020 ] tegrasign_v3.py --key None --list mb1_cold_boot_bct_MB1_aligned_sigheader.bct_list.xml --pubkeyhash pub_key.key --sha sha512
[   0.5021 ] Assuming zero filled SBK key
[   0.5031 ] Warning: pub_key.key is not found
[   0.4746 ] tegrahost_v2 --chip 0x23 0 --updatesigheader mb1_cold_boot_bct_MB1_aligned_sigheader.bct.encrypt mb1_cold_boot_bct_MB1_aligned_sigheader.bct.hash zerosbk
[   0.4752 ] Generating recovery mb1-bct
[   0.4755 ] tegrabct_v2 --chip 0x23 0 --mb1bct mb1_bct.cfg --misc tegra234-mb1-bct-misc-p3701-0000_cpp.dtb --device tegra234-mb1-bct-device-p3701-0000_cpp.dtb
[   0.4757 ] MB1-BCT version: 0.13

[   0.4772 ] Parsing config file :tegra234-mb1-bct-device-p3701-0000_cpp.dtb 
[   0.4774 ] Added Platform Config 9 data with size :- 100
[   0.4774 ] 
[   0.4774 ] Updating mb1-bct with firmware information
[   0.4776 ] tegrabct_v2 --chip 0x23 0 --mb1bct mb1_bct_MB1.bct --recov --updatefwinfo readinfo_t234_min_prod.xml.bin
[   0.4784 ] tegrahost_v2 --chip 0x23 0 --align mb1_bct_MB1_aligned.bct
[   0.4786 ] Generating SHA2 Hash for mb1bct
[   0.5079 ] Sha saved in mb1_bct_MB1_aligned.sha
[   0.5083 ] Sha saved in mb1_bct_MB1.sha
[   0.4796 ] tegrahost_v2 --chip 0x23 0 --magicid MBCT --appendsigheader mb1_bct_MB1_aligned.bct zerosbk
[   0.4798 ] adding BCH for mb1_bct_MB1_aligned.bct
[   0.5090 ] tegrasign_v3.py --key None --list mb1_bct_MB1_aligned_sigheader.bct_list.xml --pubkeyhash pub_key.key --sha sha512
[   0.5091 ] Assuming zero filled SBK key
[   0.5097 ] Warning: pub_key.key is not found
[   0.4811 ] tegrahost_v2 --chip 0x23 0 --updatesigheader mb1_bct_MB1_aligned_sigheader.bct.encrypt mb1_bct_MB1_aligned_sigheader.bct.hash zerosbk
[   0.4817 ] Info: Skip generating mem_bct because sdram_config is not defined
[   0.4817 ] Info: Skip generating mem_bct because sdram_config is not defined
[   0.4817 ] Copying signatures
[   0.4818 ] tegrahost_v2 --chip 0x23 0 --partitionlayout readinfo_t234_min_prod.xml.bin --updatesig images_list_signed.xml
[   0.4866 ] mb1_t234_prod_aligned_sigheader.bin.encrypt filename is from images_list
[   0.4867 ] psc_bl1_t234_prod_aligned_sigheader.bin.encrypt filename is from images_list
[   0.4867 ] Boot Rom communication
[   0.4869 ] tegrarcm_v2 --new_session --chip 0x23 0 --uid --download bct_br br_bct_BR.bct --download mb1 mb1_t234_prod_aligned_sigheader.bin.encrypt --download psc_bl1 psc_bl1_t234_prod_aligned_sigheader.bin.encrypt --download bct_mb1 mb1_bct_MB1_sigheader.bct.encrypt
[   0.4871 ] BR_CID: 0x80012344705DF1172C0000000D020080
[   0.5109 ] Sending bct_br
[   0.5109 ] ERROR: might be timeout in USB write.
Error: Return value 3
Command tegrarcm_v2 --new_session --chip 0x23 0 --uid --download bct_br br_bct_BR.bct --download mb1 mb1_t234_prod_aligned_sigheader.bin.encrypt --download psc_bl1 psc_bl1_t234_prod_aligned_sigheader.bin.encrypt --download bct_mb1 mb1_bct_MB1_sigheader.bct.encrypt
[  10.9374 ] tegrarcm_v2 --chip 0x23 0 --ismb2applet
[  10.9380 ] tegrarcm_v2 --chip 0x23 0 --ismb2applet
[  10.9385 ] Retrieving board information
[  10.9386 ] tegrarcm_v2 --chip 0x23 0 --oem platformdetails chip chip_info.bin
[  10.9389 ] Retrieving EEPROM data
[  10.9389 ] tegrarcm_v2 --oem platformdetails eeprom cvm /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/cvm.bin --chip 0x23 0
[  10.9393 ] tegrarcm_v2 --chip 0x23 0 --ismb2applet
[  10.9397 ] tegrarcm_v2 --chip 0x23 0 --ismb2applet
[  10.9399 ] Dumping customer Info
[  10.9401 ] tegrarcm_v2 --chip 0x23 0 --oem dump bct tmp.bct
[  10.9404 ] tegrabct_v2 --brbct tmp.bct --chip 0x23 0 --custinfo /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/custinfo_out.bin
[  10.9406 ] File tmp.bct open failed
[  10.9408 ] Error: try getting custinfo fail. Moving on
[  10.9408 ] Rebooting to recovery mode
[  10.9410 ] tegrarcm_v2 --chip 0x23 0 --ismb2
[  10.9412 ] Rebooting to recovery mode
[  10.9413 ] tegrarcm_v2 --chip 0x23 0 --reboot recovery
Board ID(3701) version(500) sku(0004) revision(F.0)
Chip SKU(00:00:00:D2) ramcode(00:00:00:00) fuselevel(fuselevel_production) board_FAB(500)
Copy /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/tegra234-p3737-0000+p3701-0004-nv.dtb to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/tegra234-p3737-0000+p3701-0004-nv.dtb.rec
copying bctfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-p3701-0000-sdram-l4t.dts)... done.
copying minratchet_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-ratchet-p3701-0000.dts)... done.
copying device_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-device-p3701-0000.dts)... done.
copying misc_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-misc-p3701-0000.dts)... done.
copying pinmux_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-pinmux-p3701-0000-a04.dtsi)... done.
copying gpioint_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-gpioint-p3701-0000.dts)... done.
copying pmic_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-pmic-p3701-0005.dts)... done.
copying pmc_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-padvoltage-p3701-0000-a04.dtsi)... done.
copying deviceprod_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-cprod-p3701-0000.dts)... done.
copying prod_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-prod-p3701-0000.dts)... done.
copying scr_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb2-bct-scr-p3701-0000.dts)... done.
copying wb0sdram(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-p3701-0000-wb0sdram-l4t.dts)... done.
copying bootrom_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb1-bct-reset-p3701-0000.dts)... done.
Existing uphylane_config(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/tegra234-mb1-bct-uphylane-si.dtsi) reused.
copying dev_params(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-br-bct-p3701-0000.dts)... done.
copying dev_params_b(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-br-bct_b-p3701-0000.dts)... done.
copying mb2bct_cfg(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/BCT/tegra234-mb2-bct-misc-p3701-0000.dts)... done.
Existing pscfwfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/pscfw_t234_prod.bin) reused.
Existing pscbl1file(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/psc_bl1_t234_prod.bin) reused.
Existing mtsmcefile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/mce_flash_o10_cr_prod.bin) reused.
Existing tscfwfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/tsec_t234.bin) reused.
Existing mb2applet(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/applet_t234.bin) reused.
Existing bootloader(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/mb2_t234.bin) reused.
copying initrd(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/l4t_initrd.img)... done.
bl is uefi
Making Boot image... done.
Not signing of boot.img
Making recovery ramdisk for recovery image...
Re-generating recovery ramdisk for recovery image...
/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/ramdisk_tmp /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra
54794 blocks

gzip: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/Image: not in gzip format
_BASE_KERNEL_VERSION=5.15.136-tegra
cp: cannot stat '/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/rootfs/usr/bin/busybox': No such file or directory
warning: cp -f /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/rootfs/usr/bin/busybox /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/ramdisk_tmp//bin/busybox
76390 blocks
Making Recovery image...
copying recdtbfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/tegra234-p3737-0000+p3701-0004-nv.dtb.rec)... done.
20+0 records in
20+0 records out
20 bytes copied, 0.000106609 s, 188 kB/s
Existing sosfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/mb1_t234_prod.bin) reused.
Existing tegraboot(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/mb2_t234.bin) reused.
Existing cpu_bootloader(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/mb2_t234.bin) reused.
Existing mb2blfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/mb2_t234.bin) reused.
Existing xusbfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/xusb_t234_prod.bin) reused.
Existing pvafile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/nvpva_020.fw) reused.
Existing dcefile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/display-t234-dce.bin) reused.
Existing nvdecfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/nvdec_t234_prod.fw) reused.
Existing psc_rf(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/psc_rf_t234_prod.bin) reused.
Existing mb2_rf(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/mb2rf_t234.bin) reused.
Existing mb1file(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/mb1_t234_prod.bin) reused.
Existing bpffile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/bpmp_t234-TE990M-A1_prod.bin) reused.
copying bpfdtbfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/tegra234-bpmp-3701-0004-3737-0000.dtb)... done.
Existing camerafw(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/camera-rtcpu-t234-rce.img) reused.
Existing apefile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/adsp-fw.bin) reused.
Existing spefile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/spe_t234.bin) reused.
Existing wb0boot(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/sc7_t234_prod.bin) reused.
Existing tosfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/tos-optee_t234.img) reused.
Existing eksfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/eks_t234.img) reused.
copying dtbfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/tegra234-p3737-0000+p3701-0004-nv.dtb)... done.
Copying nv_boot_control.conf to rootfs
Skip generating system.img
Not signing of kernel-dtb
Existing tbcfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/uefi_jetson.bin) reused.
131072+0 records in
131072+0 records out
67108864 bytes (67 MB, 64 MiB) copied, 0.321086 s, 209 MB/s
	Sync'ing esp.img ... done.
copying tbcdtbfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/tegra234-p3737-0000+p3701-0004-nv.dtb)... done.
copying cfgfile(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/generic/cfg/flash_t234_qspi_sdmmc.xml) to flash.xml... done.
Existing flashapp(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/tegraflash.py) reused.
copying overlay_dtb(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/L4TConfiguration.dtbo)... done.
copying overlay_dtb(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/tegra234-carveouts.dtbo)... done.
copying overlay_dtb(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/tegra-optee.dtbo)... done.
copying overlay_dtb(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/tegra234-p3737-camera-dual-imx274-overlay.dtbo)... done.
copying overlay_dtb(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/tegra234-p3737-camera-e3331-overlay.dtbo)... done.
copying overlay_dtb(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/tegra234-p3737-camera-e3333-overlay.dtbo)... done.
copying overlay_dtb(/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/kernel/dtb/tegra234-p3737-camera-imx185-overlay.dtbo)... done.
/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/L4TConfiguration_updated.dts: Warning (unit_address_vs_reg): Node /fragment@0 has a unit name, but no reg property
/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/L4TConfiguration.dtbo: Warning (unit_address_vs_reg): Node /fragment@0 has a unit name, but no reg property
/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/L4TConfiguration_updated.dts: Warning (unit_address_vs_reg): Node /fragment@0 has a unit name, but no reg property
/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/L4TConfiguration.dtbo: Warning (unit_address_vs_reg): Node /fragment@0 has a unit name, but no reg property
./tegraflash.py --bl uefi_jetson_with_dtb.bin --odmdata gbe-uphy-config-22,nvhs-uphy-config-0,hsio-uphy-config-0,gbe0-enable-10g,hsstp-lane-map-3 --overlay_dtb L4TConfiguration.dtbo,tegra234-carveouts.dtbo,tegra-optee.dtbo,tegra234-p3737-camera-dual-imx274-overlay.dtbo,tegra234-p3737-camera-e3331-overlay.dtbo,tegra234-p3737-camera-e3333-overlay.dtbo,tegra234-p3737-camera-imx185-overlay.dtbo, --bldtb tegra234-p3737-0000+p3701-0004-nv.dtb --applet mb1_t234_prod.bin --cmd "sign" --cfg flash.xml --chip "0x23" --concat_cpubl_bldtb --cpubl uefi_jetson.bin --minratchet_config tegra234-mb1-bct-ratchet-p3701-0000.dts --device_config tegra234-mb1-bct-device-p3701-0000.dts --misc_config tegra234-mb1-bct-misc-p3701-0000.dts --pinmux_config tegra234-mb1-bct-pinmux-p3701-0000-a04.dtsi --gpioint_config tegra234-mb1-bct-gpioint-p3701-0000.dts --pmic_config tegra234-mb1-bct-pmic-p3701-0005.dts --pmc_config tegra234-mb1-bct-padvoltage-p3701-0000-a04.dtsi --deviceprod_config tegra234-mb1-bct-cprod-p3701-0000.dts --prod_config tegra234-mb1-bct-prod-p3701-0000.dts --scr_config tegra234-mb2-bct-scr-p3701-0000.dts --wb0sdram_config tegra234-p3701-0000-wb0sdram-l4t.dts --br_cmd_config tegra234-mb1-bct-reset-p3701-0000.dts --uphy tegra234-mb1-bct-uphylane-si.dtsi --dev_params tegra234-br-bct-p3701-0000.dts,tegra234-br-bct_b-p3701-0000.dts --mb2bct_cfg tegra234-mb2-bct-misc-p3701-0000.dts --bins "psc_fw pscfw_t234_prod.bin; mts_mce mce_flash_o10_cr_prod.bin; tsec_fw tsec_t234.bin; mb2_applet applet_t234.bin; mb2_bootloader mb2_t234.bin; xusb_fw xusb_t234_prod.bin; pva_fw nvpva_020.fw; dce_fw display-t234-dce.bin; nvdec nvdec_t234_prod.fw; bpmp_fw bpmp_t234-TE990M-A1_prod.bin; bpmp_fw_dtb tegra234-bpmp-3701-0004-3737-0000.dtb; rce_fw camera-rtcpu-t234-rce.img; ape_fw adsp-fw.bin; spe_fw spe_t234.bin; tos tos-optee_t234.img; eks eks_t234.img; kernel boot.img; kernel_dtb tegra234-p3737-0000+p3701-0004-nv.dtb" --sdram_config tegra234-p3701-0000-sdram-l4t.dts --cust_info custinfo_out.bin --bct_backup --boot_chain A 
Welcome to Tegra Flash
version 1.0.0
Type ? or help for help and q or quit to exit
Use ! to execute system commands
 
[   0.0111 ] tegrasign_v3.py --key None --getmode mode.txt
[   0.0112 ] Assuming zero filled SBK key
[   0.0108 ] Parsing partition layout
[   0.0112 ] tegraparser_v2 --pt flash.xml.tmp
[   0.0141 ] Change tegra234-bpmp-3701-0004-3737-0000.dtb to tegra234-bpmp-3701-0004-3737-0000_with_odm.dtb
[   0.0141 ] Change tegra234-bpmp-3701-0004-3737-0000.dtb to tegra234-bpmp-3701-0004-3737-0000_with_odm.dtb
[   0.0464 ] /usr/bin/python3 dtbcheck.py -c t234 -o tegra234-bpmp-3701-0004-3737-0000_with_odm.dtb tegra234-bpmp-3701-0004-3737-0000_with_odm_tmp.dtb
[   0.2601 ] Concatenating L4TConfiguration.dtbo,tegra234-carveouts.dtbo,tegra-optee.dtbo,tegra234-p3737-camera-dual-imx274-overlay.dtbo,tegra234-p3737-camera-e3331-overlay.dtbo,tegra234-p3737-camera-e3333-overlay.dtbo,tegra234-p3737-camera-imx185-overlay.dtbo to tegra234-p3737-0000+p3701-0004-nv_with_odm_overlay.dtb.updated
[   0.2602 ] Concatenating bl dtb to cpubl binary
[   0.2619 ] MB2 binary: mb2_t234.bin
[   0.2620 ] Pre-processing mb2bct config: tegra234-mb2-bct-misc-p3701-0000.dts
[   0.2714 ] Pre-processing mb2bct config: tegra234-mb2-bct-scr-p3701-0000.dts
[   0.4863 ] Generating coldboot mb2-bct
[   0.4863 ] tegrabct_v2 --chip 0x23 0 --mb2bct mb2_cold_boot_bct.cfg --mb2bctcfg tegra234-mb2-bct-misc-p3701-0000_cpp.dtb --scr tegra234-mb2-bct-scr-p3701-0000_cpp.dtb
[   0.4865 ] ERROR: value 0x31 is out of range
[   0.4873 ] ERROR: value 0x31 is out of range
[   0.4874 ] ERROR: value 0x31 is out of range
[   0.4876 ] ERROR: value 0x31 is out of range
[   0.4877 ] WARNING: unknown property 'tfc_version'
[   0.4878 ] WARNING: unknown property 'addr_header_version'
[   0.4974 ] Updating mb2-bct with storage information
[   0.4977 ] tegrabct_v2 --chip 0x23 0 --mb2bct mb2_cold_boot_bct_MB2.bct --updatestorageinfo flash.xml.bin
[   0.5437 ] Concatenating mb2-bct to mb2 binary
[   0.5437 ] mb2_bin_file = mb2_t234.bin
[   0.5437 ] mb2_bct_file = mb2_cold_boot_bct_MB2.bct
[   0.6652 ] DCE binary: display-t234-dce.bin
[   0.6653 ] Kernel DTB used: kernel_tegra234-p3737-0000+p3701-0004-nv.dtb
[   0.6653 ] Concatenating kernel-dtb to dce-fw binary
[   0.6653 ] dce_bin = display-t234-dce.bin
[   0.6653 ] kernel_dtb = kernel_tegra234-p3737-0000+p3701-0004-nv.dtb
[   0.6653 ] dce_with_dtb = display-t234-dce_with_kernel_tegra234-p3737-0000+p3701-0004-nv.bin
[   0.6718 ] Update display-t234-dce_with_kernel_tegra234-p3737-0000+p3701-0004-nv.bin to dce_fw partitions
[   0.7938 ] Parsing partition layout
[   0.7944 ] tegraparser_v2 --pt flash.xml.tmp
[   0.7954 ] Creating list of images to be signed
[   0.7957 ] Generating ratchet blob
[   0.7958 ] Pre-processing config: tegra234-mb1-bct-reset-p3701-0000.dts
[   0.8012 ] Pre-processing config: tegra234-mb1-bct-device-p3701-0000.dts
[   0.8061 ] Pre-processing config: tegra234-mb1-bct-cprod-p3701-0000.dts
[   0.8110 ] Pre-processing config: tegra234-mb1-bct-gpioint-p3701-0000.dts
[   0.8171 ] Pre-processing config: tegra234-mb1-bct-misc-p3701-0000.dts
[   0.8248 ] Pre-processing config: tegra234-mb1-bct-pinmux-p3701-0000-a04.dtsi
[   1.0349 ] Pre-processing config: tegra234-mb1-bct-padvoltage-p3701-0000-a04.dtsi
[   1.0404 ] Pre-processing config: tegra234-mb1-bct-pmic-p3701-0005.dts
[   1.0461 ] Pre-processing config: tegra234-mb1-bct-prod-p3701-0000.dts
[   1.0515 ] Pre-processing config: tegra234-p3701-0000-sdram-l4t.dts
[   2.3108 ] Pre-processing config: tegra234-mb1-bct-uphylane-si.dtsi
[   2.3167 ] Pre-processing config: tegra234-p3701-0000-wb0sdram-l4t.dts
[   3.4005 ] Pre-processing config: tegra234-mb1-bct-ratchet-p3701-0000.dts
[   3.4059 ] Generating coldboot mb1-bct
[   3.4063 ] tegrabct_v2 --chip 0x23 0 --mb1bct mb1_cold_boot_bct.cfg --misc tegra234-mb1-bct-misc-p3701-0000_cpp.dtb --wb0sdram tegra234-p3701-0000-wb0sdram-l4t_cpp.dtb --pinmux tegra234-mb1-bct-pinmux-p3701-0000-a04_cpp.dtb --pmc tegra234-mb1-bct-padvoltage-p3701-0000-a04_cpp.dtb --pmic tegra234-mb1-bct-pmic-p3701-0005_cpp.dtb --brcommand tegra234-mb1-bct-reset-p3701-0000_cpp.dtb --prod tegra234-mb1-bct-prod-p3701-0000_cpp.dtb --gpioint tegra234-mb1-bct-gpioint-p3701-0000_cpp.dtb --uphy tegra234-mb1-bct-uphylane-si_cpp.dtb --device tegra234-mb1-bct-device-p3701-0000_cpp.dtb --deviceprod tegra234-mb1-bct-cprod-p3701-0000_cpp.dtb --minratchet tegra234-mb1-bct-ratchet-p3701-0000_cpp.dtb --ratchet_blob ratchet_blob.bin
[   3.4065 ] MB1-BCT version: 0.13

[   3.4079 ] Parsing config file :tegra234-mb1-bct-pinmux-p3701-0000-a04_cpp.dtb 
[   3.4082 ] Added Platform Config 0 data with size :- 3320

[   3.4101 ] Parsing config file :tegra234-mb1-bct-padvoltage-p3701-0000-a04_cpp.dtb 
[   3.4104 ] WARNING: unknown node 'g2'
[   3.4105 ] WARNING: unknown node 'g2'
[   3.4107 ] WARNING: unknown node 'g9'
[   3.4107 ] WARNING: unknown node 'g9'
[   3.4107 ] Added Platform Config 2 data with size :- 24
[   3.4107 ] 
[   3.4107 ] Parsing config file :tegra234-mb1-bct-pmic-p3701-0005_cpp.dtb 
[   3.4107 ] Added Platform Config 4 data with size :- 580
[   3.4107 ] 
[   3.4107 ] Parsing config file :tegra234-mb1-bct-reset-p3701-0000_cpp.dtb 
[   3.4107 ] Added Platform Config 3 data with size :- 52
[   3.4107 ] 
[   3.4107 ] Parsing config file :tegra234-mb1-bct-prod-p3701-0000_cpp.dtb 
[   3.4107 ] WARNING: unknown property 'major'
[   3.4107 ] WARNING: unknown property 'minor'
[   3.4107 ] Added Platform Config 5 data with size :- 524
[   3.4107 ] 
[   3.4107 ] Parsing config file :tegra234-mb1-bct-gpioint-p3701-0000_cpp.dtb 
[   3.4107 ] WARNING: unknown property 'major'
[   3.4107 ] WARNING: unknown property 'minor'
[   3.4108 ] Added Platform Config 7 data with size :- 380
[   3.4108 ] 
[   3.4108 ] Parsing config file :tegra234-mb1-bct-uphylane-si_cpp.dtb 
[   3.4108 ] Added Platform Config 8 data with size :- 24
[   3.4108 ] 
[   3.4108 ] Parsing config file :tegra234-mb1-bct-device-p3701-0000_cpp.dtb 
[   3.4108 ] Added Platform Config 9 data with size :- 100
[   3.4108 ] 
[   3.4108 ] Parsing config file :tegra234-mb1-bct-cprod-p3701-0000_cpp.dtb 
[   3.4108 ] ModuleCount 0 NumProdNames 0
[   3.4108 ] Added Platform Config 6 data with size :- 16
[   3.4108 ] 
[   3.4108 ] Parsing config file :tegra234-mb1-bct-ratchet-p3701-0000_cpp.dtb 
[   3.4108 ] 
[   3.4108 ] Updating mb1-bct with firmware information
[   3.4112 ] tegrabct_v2 --chip 0x23 0 --mb1bct mb1_cold_boot_bct_MB1.bct --updatefwinfo flash.xml.bin
[   3.4460 ] tegrahost_v2 --chip 0x23 0 --align mb1_cold_boot_bct_MB1_aligned.bct
[   3.4464 ] Generating SHA2 Hash for mb1bct
[   3.4477 ] Sha saved in mb1_cold_boot_bct_MB1_aligned.sha
[   3.4484 ] Sha saved in mb1_cold_boot_bct_MB1.sha
[   3.4483 ] tegrahost_v2 --chip 0x23 0 --magicid MBCT --ratchet_blob ratchet_blob.bin --appendsigheader mb1_cold_boot_bct_MB1_aligned.bct zerosbk
[   3.4485 ] adding BCH for mb1_cold_boot_bct_MB1_aligned.bct
[   3.4496 ] tegrasign_v3.py --key None --list mb1_cold_boot_bct_MB1_aligned_sigheader.bct_list.xml --pubkeyhash pub_key.key --sha sha512
[   3.4498 ] Assuming zero filled SBK key
[   3.4508 ] Warning: pub_key.key is not found
[   3.4507 ] tegrahost_v2 --chip 0x23 0 --updatesigheader mb1_cold_boot_bct_MB1_aligned_sigheader.bct.encrypt mb1_cold_boot_bct_MB1_aligned_sigheader.bct.hash zerosbk
[   3.4515 ] tegrahost_v2 --chip 0x23 0 --partitionlayout flash.xml.bin --ratchet_blob ratchet_blob.bin --list images_list.xml zerosbk
[   3.4517 ] MB1: Nvheader already present is mb1_t234_prod_aligned.bin
[   3.4526 ] Header already present for mb1_t234_prod_aligned_sigheader.bin
[   3.4529 ] MB1: Nvheader already present is psc_bl1_t234_prod_aligned.bin
[   3.4560 ] Header already present for psc_bl1_t234_prod_aligned_sigheader.bin
[   3.4561 ] Header already present for tsec_t234_aligned.bin
[   3.4571 ] Header already present for nvdec_t234_prod_aligned.fw
[   3.4587 ] adding BCH for mb2_t234_with_mb2_cold_boot_bct_MB2_aligned.bin
[   3.4615 ] adding BCH for xusb_t234_prod_aligned.bin
[   3.4680 ] Header already present for bpmp_t234-TE990M-A1_prod_aligned.bin
[   3.4719 ] adding BCH for tegra234-bpmp-3701-0004-3737-0000_with_odm_aligned.dtb
[   3.4797 ] Header already present for pscfw_t234_prod_aligned.bin
[   3.4858 ] Header already present for mce_flash_o10_cr_prod_aligned.bin
[   3.4882 ] Header already present for sc7_t234_prod.bin
[   3.4895 ] Header already present for psc_rf_t234_prod_aligned.bin
[   3.4911 ] adding BCH for mb2rf_t234_aligned.bin
[   3.4920 ] INFO: compressing uefi_jetson_with_dtb_aligned.bin
[   3.5235 ] INFO: complete compression, uefi_jetson_with_dtb_aligned.bin, ratio = 90%
[   3.5274 ] adding BCH for uefi_jetson_with_dtb_aligned_blob_w_bin_aligned.bin
[   3.5564 ] adding BCH for tos-optee_t234_aligned.img
[   3.5835 ] adding BCH for eks_t234_aligned.img
[   3.6072 ] INFO: compressing display-t234-dce_with_kernel_tegra234-p3737-0000+p3701-0004-nv_aligned.bin
[   3.7114 ] INFO: complete compression, display-t234-dce_with_kernel_tegra234-p3737-0000+p3701-0004-nv_aligned.bin, ratio = 6%
[   3.7218 ] adding BCH for display-t234-dce_with_kernel_tegra234-p3737-0000+p3701-0004-nv_aligned_blob_w_bin_aligned.bin
[   3.7324 ] adding BCH for spe_t234_aligned.bin
[   3.7385 ] adding BCH for camera-rtcpu-t234-rce_aligned.img
[   3.7428 ] adding BCH for adsp-fw_aligned.bin
[   3.7497 ] INFO: compressing nvpva_020_aligned.fw
[   3.7734 ] INFO: complete compression, nvpva_020_aligned.fw, ratio = 2%
[   3.7748 ] adding BCH for nvpva_020_aligned_blob_w_bin_aligned.fw
[   3.7760 ] MB1: Nvheader already present is mb1_t234_prod_aligned.bin
[   3.7769 ] Header already present for mb1_t234_prod_aligned_sigheader.bin
[   3.7770 ] MB1: Nvheader already present is psc_bl1_t234_prod_aligned.bin
[   3.7794 ] Header already present for psc_bl1_t234_prod_aligned_sigheader.bin
[   3.7795 ] Header already present for tsec_t234_aligned.bin
[   3.7810 ] Header already present for nvdec_t234_prod_aligned.fw
[   3.7826 ] adding BCH for mb2_t234_with_mb2_cold_boot_bct_MB2_aligned.bin
[   3.7855 ] adding BCH for xusb_t234_prod_aligned.bin
[   3.7924 ] Header already present for bpmp_t234-TE990M-A1_prod_aligned.bin
[   3.7964 ] adding BCH for tegra234-bpmp-3701-0004-3737-0000_with_odm_aligned.dtb
[   3.8050 ] Header already present for pscfw_t234_prod_aligned.bin
[   3.8108 ] Header already present for mce_flash_o10_cr_prod_aligned.bin
[   3.8133 ] Header already present for sc7_t234_prod.bin
[   3.8149 ] Header already present for psc_rf_t234_prod_aligned.bin
[   3.8165 ] adding BCH for mb2rf_t234_aligned.bin
[   3.8176 ] INFO: compressing uefi_jetson_with_dtb_aligned.bin
[   3.8509 ] INFO: complete compression, uefi_jetson_with_dtb_aligned.bin, ratio = 90%
[   3.8547 ] adding BCH for uefi_jetson_with_dtb_aligned_blob_w_bin_aligned.bin
[   3.8852 ] adding BCH for tos-optee_t234_aligned.img
[   3.9136 ] adding BCH for eks_t234_aligned.img
[   3.9380 ] INFO: compressing display-t234-dce_with_kernel_tegra234-p3737-0000+p3701-0004-nv_aligned.bin
[   4.0406 ] INFO: complete compression, display-t234-dce_with_kernel_tegra234-p3737-0000+p3701-0004-nv_aligned.bin, ratio = 6%
[   4.0509 ] adding BCH for display-t234-dce_with_kernel_tegra234-p3737-0000+p3701-0004-nv_aligned_blob_w_bin_aligned.bin
[   4.0618 ] adding BCH for spe_t234_aligned.bin
[   4.0684 ] adding BCH for camera-rtcpu-t234-rce_aligned.img
[   4.0728 ] adding BCH for adsp-fw_aligned.bin
[   4.0800 ] INFO: compressing nvpva_020_aligned.fw
[   4.1039 ] INFO: complete compression, nvpva_020_aligned.fw, ratio = 2%
[   4.1053 ] adding BCH for nvpva_020_aligned_blob_w_bin_aligned.fw
[   4.1071 ] Filling MB1 storage info
[   4.1071 ] Parsing dev params for multi chains
[   4.1129 ] Generating br-bct
[   4.1131 ] Updating dev and MSS params in BR BCT
[   4.1131 ] tegrabct_v2 --dev_param tegra234-br-bct-p3701-0000_cpp.dtb --sdram tegra234-p3701-0000-sdram-l4t_cpp.dtb --brbct br_bct.cfg --chip 0x23 0
[   4.1729 ] Updating bl info
[   4.1733 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updateblinfo flash.xml.bin
[   4.1785 ] Generating br-bct
[   4.1786 ] Updating dev and MSS params in BR BCT
[   4.1787 ] tegrabct_v2 --dev_param tegra234-br-bct_b-p3701-0000_cpp.dtb --sdram tegra234-p3701-0000-sdram-l4t_cpp.dtb --brbct br_bct.cfg --chip 0x23 0
[   4.2421 ] Updating bl info
[   4.2423 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updateblinfo flash.xml.bin
[   4.2433 ] Generating BCT backup image
[   4.2433 ] dd if=/dev/zero of=bct_backup.img bs=1 count=32768
[   4.2435 ] 32768+0 records in
[   4.2575 ] 32768+0 records out
[   4.2575 ] 32768 bytes (33 kB, 32 KiB) copied, 0.0135496 s, 2.4 MB/s
[   4.2575 ] 
[   4.2576 ] Concatenating BCT for chain A to bct_backup.img

[   4.2576 ] dd if=br_bct_BR.bct of=bct_backup.img bs=1 seek=0 conv=notrunc
[   4.2577 ] 8192+0 records in
[   4.2651 ] 8192+0 records out
[   4.2651 ] 8192 bytes (8.2 kB, 8.0 KiB) copied, 0.00693304 s, 1.2 MB/s
[   4.2651 ] 
[   4.2652 ] Concatenating BCT for chain B to bct_backup.img

[   4.2652 ] dd if=br_bct_b_BR.bct of=bct_backup.img bs=1 seek=16384 conv=notrunc
[   4.2654 ] 8192+0 records in
[   4.2728 ] 8192+0 records out
[   4.2728 ] 8192 bytes (8.2 kB, 8.0 KiB) copied, 0.0069891 s, 1.2 MB/s
[   4.2728 ] 
[   4.2729 ] Generating signatures
[   4.2733 ] tegrasign_v3.py --key None --list images_list.xml --pubkeyhash pub_key.key --sha sha512
[   4.2734 ] Assuming zero filled SBK key
[   4.4709 ] Warning: pub_key.key is not found
[   4.4719 ] Parsing dev params for multi chains
[   4.4719 ] Generating br-bct
[   4.4722 ] Updating dev and MSS params in BR BCT
[   4.4722 ] tegrabct_v2 --dev_param tegra234-br-bct-p3701-0000_cpp.dtb --sdram tegra234-p3701-0000-sdram-l4t_cpp.dtb --brbct br_bct.cfg --chip 0x23 0
[   4.5345 ] Updating customer data section
[   4.5347 ] tegrabct_v2 --chip 0x23 0 --brbct br_bct_BR.bct --update_custinfo custinfo_out.bin
[   4.5360 ] Updating bl info
[   4.5363 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updateblinfo flash.xml.bin --updatesig images_list_signed.xml
[   4.5378 ] Generating SHA2 Hash
[   4.5387 ] Sha saved in br_bct_BR.sha
[   4.5383 ] Get Signed section of bct
[   4.5385 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --listbct bct_list.xml
[   4.5388 ] Signing BCT
[   4.5392 ] tegrasign_v3.py --key None --list bct_list.xml --pubkeyhash pub_key.key --sha sha512
[   4.5393 ] Assuming zero filled SBK key
[   4.5402 ] Sha saved in br_bct_BR.sha
[   4.5403 ] Warning: pub_key.key is not found
[   4.5399 ] Updating BCT with signature
[   4.5401 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updatesig bct_list_signed.xml
[   4.5402 ] Offset :4608 Len :3584
[   4.5408 ] Generating SHA2 Hash
[   4.5412 ] tegrasign_v3.py --key None --list bct_list.xml --sha sha512
[   4.5413 ] Assuming zero filled SBK key
[   4.5413 ] Assuming zero filled SBK key
[   4.5429 ] Sha saved in br_bct_BR.sha
[   4.5427 ] Updating BCT with SHA2 Hash
[   4.5431 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updatesha bct_list_signed.xml
[   4.5434 ] Offset :4608 Len :3584
[   4.5437 ] Offset :68 Len :8124
[   4.5440 ] Generating br-bct
[   4.5443 ] Updating dev and MSS params in BR BCT
[   4.5443 ] tegrabct_v2 --dev_param tegra234-br-bct_b-p3701-0000_cpp.dtb --sdram tegra234-p3701-0000-sdram-l4t_cpp.dtb --brbct br_bct.cfg --chip 0x23 0
[   4.6092 ] Updating customer data section
[   4.6095 ] tegrabct_v2 --chip 0x23 0 --brbct br_bct_BR.bct --update_custinfo custinfo_out.bin
[   4.6137 ] Updating bl info
[   4.6141 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updateblinfo flash.xml.bin --updatesig images_list_signed.xml
[   4.9358 ] Generating SHA2 Hash
[   4.9371 ] Sha saved in br_bct_BR.sha
[   4.9367 ] Get Signed section of bct
[   4.9369 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --listbct bct_list.xml
[   4.9466 ] Signing BCT
[   4.9471 ] tegrasign_v3.py --key None --list bct_list.xml --pubkeyhash pub_key.key --sha sha512
[   4.9471 ] Assuming zero filled SBK key
[   4.9482 ] Sha saved in br_bct_BR.sha
[   4.9484 ] Warning: pub_key.key is not found
[   4.9480 ] Updating BCT with signature
[   4.9481 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updatesig bct_list_signed.xml
[   4.9483 ] Offset :4608 Len :3584
[   4.9597 ] Generating SHA2 Hash
[   4.9601 ] tegrasign_v3.py --key None --list bct_list.xml --sha sha512
[   4.9602 ] Assuming zero filled SBK key
[   4.9603 ] Assuming zero filled SBK key
[   4.9618 ] Sha saved in br_bct_BR.sha
[   4.9616 ] Updating BCT with SHA2 Hash
[   4.9618 ] tegrabct_v2 --brbct br_bct_BR.bct --chip 0x23 0 --updatesha bct_list_signed.xml
[   4.9621 ] Offset :4608 Len :3584
[   4.9624 ] Offset :68 Len :8124
[   4.9627 ] Generating BCT backup image
[   4.9627 ] dd if=/dev/zero of=bct_backup.img bs=1 count=32768
[   4.9630 ] 32768+0 records in
[   4.9810 ] 32768+0 records out
[   4.9810 ] 32768 bytes (33 kB, 32 KiB) copied, 0.0174524 s, 1.9 MB/s
[   4.9810 ] 
[   4.9810 ] Concatenating BCT for chain A to bct_backup.img

[   4.9810 ] dd if=br_bct_BR.bct of=bct_backup.img bs=1 seek=0 conv=notrunc
[   4.9813 ] 8192+0 records in
[   4.9887 ] 8192+0 records out
[   4.9887 ] 8192 bytes (8.2 kB, 8.0 KiB) copied, 0.00701751 s, 1.2 MB/s
[   4.9888 ] 
[   4.9888 ] Concatenating BCT for chain B to bct_backup.img

[   4.9888 ] dd if=br_bct_b_BR.bct of=bct_backup.img bs=1 seek=16384 conv=notrunc
[   4.9891 ] 8192+0 records in
[   4.9966 ] 8192+0 records out
[   4.9966 ] 8192 bytes (8.2 kB, 8.0 KiB) copied, 0.00706159 s, 1.2 MB/s
[   4.9966 ] 
[   4.9966 ] Generating coldboot mb1-bct
[   4.9968 ] tegrabct_v2 --chip 0x23 0 --mb1bct mb1_cold_boot_bct.cfg --misc tegra234-mb1-bct-misc-p3701-0000_cpp.dtb --wb0sdram tegra234-p3701-0000-wb0sdram-l4t_cpp.dtb --pinmux tegra234-mb1-bct-pinmux-p3701-0000-a04_cpp.dtb --pmc tegra234-mb1-bct-padvoltage-p3701-0000-a04_cpp.dtb --pmic tegra234-mb1-bct-pmic-p3701-0005_cpp.dtb --brcommand tegra234-mb1-bct-reset-p3701-0000_cpp.dtb --prod tegra234-mb1-bct-prod-p3701-0000_cpp.dtb --gpioint tegra234-mb1-bct-gpioint-p3701-0000_cpp.dtb --uphy tegra234-mb1-bct-uphylane-si_cpp.dtb --device tegra234-mb1-bct-device-p3701-0000_cpp.dtb --deviceprod tegra234-mb1-bct-cprod-p3701-0000_cpp.dtb --minratchet tegra234-mb1-bct-ratchet-p3701-0000_cpp.dtb --ratchet_blob ratchet_blob.bin
[   4.9972 ] MB1-BCT version: 0.13

[   4.9988 ] Parsing config file :tegra234-mb1-bct-pinmux-p3701-0000-a04_cpp.dtb 
[   4.9989 ] Added Platform Config 0 data with size :- 3320

[   5.0017 ] Parsing config file :tegra234-mb1-bct-padvoltage-p3701-0000-a04_cpp.dtb 
[   5.0018 ] WARNING: unknown node 'g2'
[   5.0018 ] WARNING: unknown node 'g2'
[   5.0019 ] WARNING: unknown node 'g9'
[   5.0019 ] WARNING: unknown node 'g9'
[   5.0020 ] Added Platform Config 2 data with size :- 24

[   5.0021 ] Parsing config file :tegra234-mb1-bct-pmic-p3701-0005_cpp.dtb 
[   5.0022 ] Added Platform Config 4 data with size :- 580
[   5.0022 ] 
[   5.0022 ] Parsing config file :tegra234-mb1-bct-reset-p3701-0000_cpp.dtb 
[   5.0022 ] Added Platform Config 3 data with size :- 52
[   5.0022 ] 
[   5.0022 ] Parsing config file :tegra234-mb1-bct-prod-p3701-0000_cpp.dtb 
[   5.0022 ] WARNING: unknown property 'major'
[   5.0022 ] WARNING: unknown property 'minor'
[   5.0022 ] Added Platform Config 5 data with size :- 524
[   5.0022 ] 
[   5.0022 ] Parsing config file :tegra234-mb1-bct-gpioint-p3701-0000_cpp.dtb 
[   5.0022 ] WARNING: unknown property 'major'
[   5.0022 ] WARNING: unknown property 'minor'
[   5.0022 ] Added Platform Config 7 data with size :- 380
[   5.0022 ] 
[   5.0023 ] Parsing config file :tegra234-mb1-bct-uphylane-si_cpp.dtb 
[   5.0023 ] Added Platform Config 8 data with size :- 24
[   5.0023 ] 
[   5.0023 ] Parsing config file :tegra234-mb1-bct-device-p3701-0000_cpp.dtb 
[   5.0023 ] Added Platform Config 9 data with size :- 100
[   5.0023 ] 
[   5.0023 ] Parsing config file :tegra234-mb1-bct-cprod-p3701-0000_cpp.dtb 
[   5.0023 ] ModuleCount 0 NumProdNames 0
[   5.0023 ] Added Platform Config 6 data with size :- 16
[   5.0023 ] 
[   5.0023 ] Parsing config file :tegra234-mb1-bct-ratchet-p3701-0000_cpp.dtb 
[   5.0023 ] 
[   5.0023 ] Updating mb1-bct with firmware information
[   5.0025 ] tegrabct_v2 --chip 0x23 0 --mb1bct mb1_cold_boot_bct_MB1.bct --updatefwinfo flash.xml.bin
[   5.0035 ] tegrahost_v2 --chip 0x23 0 --align mb1_cold_boot_bct_MB1_aligned.bct
[   5.0037 ] Generating SHA2 Hash for mb1bct
[   5.0047 ] Sha saved in mb1_cold_boot_bct_MB1_aligned.sha
[   5.0053 ] Sha saved in mb1_cold_boot_bct_MB1.sha
[   5.0051 ] tegrahost_v2 --chip 0x23 0 --magicid MBCT --ratchet_blob ratchet_blob.bin --appendsigheader mb1_cold_boot_bct_MB1_aligned.bct zerosbk
[   5.0053 ] adding BCH for mb1_cold_boot_bct_MB1_aligned.bct
[   5.0064 ] tegrasign_v3.py --key None --list mb1_cold_boot_bct_MB1_aligned_sigheader.bct_list.xml --pubkeyhash pub_key.key --sha sha512
[   5.0066 ] Assuming zero filled SBK key
[   5.0076 ] Warning: pub_key.key is not found
[   5.0075 ] tegrahost_v2 --chip 0x23 0 --updatesigheader mb1_cold_boot_bct_MB1_aligned_sigheader.bct.encrypt mb1_cold_boot_bct_MB1_aligned_sigheader.bct.hash zerosbk
[   5.0080 ] Generating recovery mb1-bct
[   5.0082 ] tegrabct_v2 --chip 0x23 0 --mb1bct mb1_bct.cfg --misc tegra234-mb1-bct-misc-p3701-0000_cpp.dtb --wb0sdram tegra234-p3701-0000-wb0sdram-l4t_cpp.dtb --pinmux tegra234-mb1-bct-pinmux-p3701-0000-a04_cpp.dtb --pmc tegra234-mb1-bct-padvoltage-p3701-0000-a04_cpp.dtb --pmic tegra234-mb1-bct-pmic-p3701-0005_cpp.dtb --brcommand tegra234-mb1-bct-reset-p3701-0000_cpp.dtb --prod tegra234-mb1-bct-prod-p3701-0000_cpp.dtb --gpioint tegra234-mb1-bct-gpioint-p3701-0000_cpp.dtb --uphy tegra234-mb1-bct-uphylane-si_cpp.dtb --device tegra234-mb1-bct-device-p3701-0000_cpp.dtb --deviceprod tegra234-mb1-bct-cprod-p3701-0000_cpp.dtb --minratchet tegra234-mb1-bct-ratchet-p3701-0000_cpp.dtb --ratchet_blob ratchet_blob.bin
[   5.0084 ] MB1-BCT version: 0.13

[   5.0097 ] Parsing config file :tegra234-mb1-bct-pinmux-p3701-0000-a04_cpp.dtb 
[   5.0100 ] Added Platform Config 0 data with size :- 3320

[   5.0124 ] Parsing config file :tegra234-mb1-bct-padvoltage-p3701-0000-a04_cpp.dtb 
[   5.0125 ] WARNING: unknown node 'g2'
[   5.0126 ] WARNING: unknown node 'g2'
[   5.0126 ] WARNING: unknown node 'g9'
[   5.0127 ] WARNING: unknown node 'g9'
[   5.0127 ] Added Platform Config 2 data with size :- 24

[   5.0128 ] Parsing config file :tegra234-mb1-bct-pmic-p3701-0005_cpp.dtb 
[   5.0129 ] Added Platform Config 4 data with size :- 580
[   5.0129 ] 
[   5.0129 ] Parsing config file :tegra234-mb1-bct-reset-p3701-0000_cpp.dtb 
[   5.0129 ] Added Platform Config 3 data with size :- 52
[   5.0129 ] 
[   5.0129 ] Parsing config file :tegra234-mb1-bct-prod-p3701-0000_cpp.dtb 
[   5.0129 ] WARNING: unknown property 'major'
[   5.0129 ] WARNING: unknown property 'minor'
[   5.0130 ] Added Platform Config 5 data with size :- 524
[   5.0130 ] 
[   5.0130 ] Parsing config file :tegra234-mb1-bct-gpioint-p3701-0000_cpp.dtb 
[   5.0130 ] WARNING: unknown property 'major'
[   5.0130 ] WARNING: unknown property 'minor'
[   5.0130 ] Added Platform Config 7 data with size :- 380
[   5.0130 ] 
[   5.0130 ] Parsing config file :tegra234-mb1-bct-uphylane-si_cpp.dtb 
[   5.0130 ] Added Platform Config 8 data with size :- 24
[   5.0130 ] 
[   5.0130 ] Parsing config file :tegra234-mb1-bct-device-p3701-0000_cpp.dtb 
[   5.0130 ] Added Platform Config 9 data with size :- 100
[   5.0130 ] 
[   5.0130 ] Parsing config file :tegra234-mb1-bct-cprod-p3701-0000_cpp.dtb 
[   5.0130 ] ModuleCount 0 NumProdNames 0
[   5.0130 ] Added Platform Config 6 data with size :- 16
[   5.0130 ] 
[   5.0130 ] Parsing config file :tegra234-mb1-bct-ratchet-p3701-0000_cpp.dtb 
[   5.0130 ] 
[   5.0130 ] Updating mb1-bct with firmware information
[   5.0132 ] tegrabct_v2 --chip 0x23 0 --mb1bct mb1_bct_MB1.bct --recov --updatefwinfo flash.xml.bin
[   5.0141 ] tegrahost_v2 --chip 0x23 0 --align mb1_bct_MB1_aligned.bct
[   5.0143 ] Generating SHA2 Hash for mb1bct
[   5.0152 ] Sha saved in mb1_bct_MB1_aligned.sha
[   5.0157 ] Sha saved in mb1_bct_MB1.sha
[   5.0155 ] tegrahost_v2 --chip 0x23 0 --magicid MBCT --ratchet_blob ratchet_blob.bin --appendsigheader mb1_bct_MB1_aligned.bct zerosbk
[   5.0156 ] adding BCH for mb1_bct_MB1_aligned.bct
[   5.0168 ] tegrasign_v3.py --key None --list mb1_bct_MB1_aligned_sigheader.bct_list.xml --pubkeyhash pub_key.key --sha sha512
[   5.0169 ] Assuming zero filled SBK key
[   5.0177 ] Warning: pub_key.key is not found
[   5.0176 ] tegrahost_v2 --chip 0x23 0 --updatesigheader mb1_bct_MB1_aligned_sigheader.bct.encrypt mb1_bct_MB1_aligned_sigheader.bct.hash zerosbk
[   5.0182 ] Generating coldboot mem-bct
[   5.0184 ] tegrabct_v2 --chip 0x23 0 --sdram tegra234-p3701-0000-sdram-l4t_cpp.dtb --wb0sdram tegra234-p3701-0000-wb0sdram-l4t_cpp.dtb --membct tegra234-p3701-0000-sdram-l4t_cpp_1.bct tegra234-p3701-0000-sdram-l4t_cpp_2.bct tegra234-p3701-0000-sdram-l4t_cpp_3.bct tegra234-p3701-0000-sdram-l4t_cpp_4.bct
[   5.0185 ]  packing sdram params with Wb0 file tegra234-p3701-0000-wb0sdram-l4t_cpp.dtb
[   5.0817 ] Packing sdram param for instance[0]
[   5.0818 ] Packing sdram param for instance[1]
[   5.0818 ] Packing sdram param for instance[2]
[   5.0819 ] Packing sdram param for instance[3]
[   5.0820 ] Packing sdram param for instance[4]
[   5.0821 ] Packing sdram param for instance[5]
[   5.0822 ] Packing sdram param for instance[6]
[   5.0822 ] Packing sdram param for instance[7]
[   5.0823 ] Packing sdram param for instance[8]
[   5.0824 ] Packing sdram param for instance[9]
[   5.0825 ] Packing sdram param for instance[10]
[   5.0825 ] Packing sdram param for instance[11]
[   5.0826 ] Packing sdram param for instance[12]
[   5.0827 ] Packing sdram param for instance[13]
[   5.0828 ] Packing sdram param for instance[14]
[   5.0828 ] Packing sdram param for instance[15]
[   5.1408 ] Getting sector size from pt
[   5.1412 ] tegraparser_v2 --getsectorsize flash.xml.bin sector_info.bin
[   5.1416 ] BlockSize read from layout is 0x200

[   5.1417 ] tegrahost_v2 --chip 0x23 0 --blocksize 512 --magicid MEMB --addsigheader_multi tegra234-p3701-0000-sdram-l4t_cpp_1.bct tegra234-p3701-0000-sdram-l4t_cpp_2.bct tegra234-p3701-0000-sdram-l4t_cpp_3.bct tegra234-p3701-0000-sdram-l4t_cpp_4.bct
[   5.1419 ] Binary 0 length is 58752
[   5.1421 ] Binary 0 align length is 58880
[   5.1427 ] Binary 1 length is 58752
[   5.1428 ] Binary 1 align length is 58880
[   5.1434 ] Binary 2 length is 58752
[   5.1435 ] Binary 2 align length is 58880
[   5.1441 ] Binary 3 length is 58752
[   5.1442 ] Binary 3 align length is 58880
[   5.1446 ] Buffer length is 235520
[   5.1447 ] adding BCH for tegra234-p3701-0000-sdram-l4t_cpp_1.bct
[   5.1448 ] new length is 243712
[   5.1454 ] tegrahost_v2 --chip 0x23 0 --align mem_coldboot_aligned.bct
[   5.1458 ] tegrahost_v2 --chip 0x23 0 --magicid MEMB --ratchet_blob ratchet_blob.bin --appendsigheader mem_coldboot_aligned.bct zerosbk
[   5.1460 ] Header already present for mem_coldboot_aligned.bct
[   5.1471 ] tegrasign_v3.py --key None --list mem_coldboot_aligned_sigheader.bct_list.xml --pubkeyhash pub_key.key --sha sha512
[   5.1472 ] Assuming zero filled SBK key
[   5.1484 ] Warning: pub_key.key is not found
[   5.1483 ] tegrahost_v2 --chip 0x23 0 --updatesigheader mem_coldboot_aligned_sigheader.bct.encrypt mem_coldboot_aligned_sigheader.bct.hash zerosbk
[   5.1494 ] Generating recovery mem-bct
[   5.1497 ] tegrabct_v2 --chip 0x23 0 --sdram tegra234-p3701-0000-sdram-l4t_cpp.dtb --wb0sdram tegra234-p3701-0000-wb0sdram-l4t_cpp.dtb --membct tegra234-p3701-0000-sdram-l4t_cpp_1.bct tegra234-p3701-0000-sdram-l4t_cpp_2.bct tegra234-p3701-0000-sdram-l4t_cpp_3.bct tegra234-p3701-0000-sdram-l4t_cpp_4.bct
[   5.1499 ]  packing sdram params with Wb0 file tegra234-p3701-0000-wb0sdram-l4t_cpp.dtb
[   5.2150 ] Packing sdram param for instance[0]
[   5.2151 ] Packing sdram param for instance[1]
[   5.2151 ] Packing sdram param for instance[2]
[   5.2152 ] Packing sdram param for instance[3]
[   5.2152 ] Packing sdram param for instance[4]
[   5.2153 ] Packing sdram param for instance[5]
[   5.2154 ] Packing sdram param for instance[6]
[   5.2154 ] Packing sdram param for instance[7]
[   5.2155 ] Packing sdram param for instance[8]
[   5.2156 ] Packing sdram param for instance[9]
[   5.2157 ] Packing sdram param for instance[10]
[   5.2157 ] Packing sdram param for instance[11]
[   5.2158 ] Packing sdram param for instance[12]
[   5.2159 ] Packing sdram param for instance[13]
[   5.2160 ] Packing sdram param for instance[14]
[   5.2161 ] Packing sdram param for instance[15]
[   5.2742 ] Reading ramcode from backup chip_info.bin file
[   5.2743 ] RAMCODE Read from Device: 0

[   5.2743 ] Using ramcode 0
[   5.2743 ] Disabled BPMP dtb trim, using default dtb
[   5.2743 ] 
[   5.2746 ] tegrahost_v2 --chip 0x23 0 --align mem_rcm_aligned.bct
[   5.2751 ] tegrahost_v2 --chip 0x23 0 --magicid MEM0 --ratchet_blob ratchet_blob.bin --appendsigheader mem_rcm_aligned.bct zerosbk
[   5.2752 ] adding BCH for mem_rcm_aligned.bct
[   5.2775 ] tegrasign_v3.py --key None --list mem_rcm_aligned_sigheader.bct_list.xml --pubkeyhash pub_key.key --sha sha512
[   5.2776 ] Assuming zero filled SBK key
[   5.2788 ] Warning: pub_key.key is not found
[   5.2787 ] tegrahost_v2 --chip 0x23 0 --updatesigheader mem_rcm_aligned_sigheader.bct.encrypt mem_rcm_aligned_sigheader.bct.hash zerosbk
[   5.2795 ] Copying signatures
[   5.2798 ] tegrahost_v2 --chip 0x23 0 --partitionlayout flash.xml.bin --updatesig images_list_signed.xml
[   6.2494 ] tegraparser_v2 --generategpt --pt flash.xml.bin
[   6.2497 ] gpt_secondary_3_0.bin:
[   6.2501 ] partition_id	partition_name			      StartingLba	EndingLba
[   6.2503 ]            1	BCT                                 	       0    2047
[   6.2506 ]            2	A_mb1                               	    2048    3071
[   6.2509 ]            3	A_psc_bl1                           	    3072    3583
[   6.2511 ]            4	A_MB1_BCT                           	    3584    3839
[   6.2514 ]            5	A_MEM_BCT                           	    3840    4351
[   6.2517 ]            6	A_tsec-fw                           	    4352    6399
[   6.2520 ]            7	A_nvdec                             	    6400    8447
[   6.2522 ]            8	A_mb2                               	    8448    9471
[   6.2525 ]            9	A_xusb-fw                           	    9472    9983
[   6.2528 ]           10	A_bpmp-fw                           	    9984   13055
[   6.2529 ]           11	A_bpmp-fw-dtb                       	   13056   21247
[   6.2529 ]           12	A_psc-fw                            	   21248   22783
[   6.2529 ]           13	A_mts-mce                           	   22784   23807
[   6.2529 ]           14	A_sc7                               	   23808   24191
[   6.2529 ]           15	A_pscrf                             	   24192   24575
[   6.2529 ]           16	A_mb2rf                             	   24576   24831
[   6.2529 ]           17	A_cpu-bootloader                    	   24832   31999
[   6.2529 ]           18	A_secure-os                         	   32000   40191
[   6.2529 ]           19	A_smm-fw                            	   40192   44287
[   6.2529 ]           20	A_eks                               	   44288   44799
[   6.2529 ]           21	A_dce-fw                            	   44800   55039
[   6.2529 ]           22	A_spe-fw                            	   55040   56191
[   6.2529 ]           23	A_rce-fw                            	   56192   58239
[   6.2529 ]           24	A_adsp-fw                           	   58240   62335
[   6.2530 ]           25	A_pva-fw                            	   62336   62847
[   6.2530 ]           26	A_reserved_on_boot                  	   62848   65023
[   6.2530 ]           27	B_mb1                               	   65024   66047
[   6.2530 ]           28	B_psc_bl1                           	   66048   66559
[   6.2530 ]           29	B_MB1_BCT                           	   66560   66815
[   6.2530 ]           30	B_MEM_BCT                           	   66816   67327
[   6.2530 ]           31	B_tsec-fw                           	   67328   69375
[   6.2530 ]           32	B_nvdec                             	   69376   71423
[   6.2530 ]           33	B_mb2                               	   71424   72447
[   6.2530 ]           34	B_xusb-fw                           	   72448   72959
[   6.2530 ]           35	B_bpmp-fw                           	   72960   76031
[   6.2530 ]           36	B_bpmp-fw-dtb                       	   76032   84223
[   6.2530 ]           37	B_psc-fw                            	   84224   85759
[   6.2530 ]           38	B_mts-mce                           	   85760   86783
[   6.2530 ]           39	B_sc7                               	   86784   87167
[   6.2530 ]           40	B_pscrf                             	   87168   87551
[   6.2530 ]           41	B_mb2rf                             	   87552   87807
[   6.2530 ]           42	B_cpu-bootloader                    	   87808   94975
[   6.2530 ]           43	B_secure-os                         	   94976  103167
[   6.2530 ]           44	B_smm-fw                            	  103168  107263
[   6.2530 ]           45	B_eks                               	  107264  107775
[   6.2530 ]           46	B_dce-fw                            	  107776  118015
[   6.2531 ]           47	B_spe-fw                            	  118016  119167
[   6.2531 ]           48	B_rce-fw                            	  119168  121215
[   6.2531 ]           49	B_adsp-fw                           	  121216  125311
[   6.2531 ]           50	B_pva-fw                            	  125312  125823
[   6.2531 ]           51	B_reserved_on_boot                  	  125824  127999
[   6.2531 ]           52	uefi_variables                      	  128000  128511
[   6.2531 ]           53	uefi_ftw                            	  128512  129535
[   6.2531 ]           54	reserved                            	  129536  129919
[   6.2531 ]           55	worm                                	  129920  130303
[   6.2531 ]           56	BCT-boot-chain_backup               	  130304  130431
[   6.2531 ]           57	reserved_partition                  	  130432  130559
[   6.2531 ]           58	secondary_gpt_backup                	  130560  130687
[   6.2531 ]           59	B_VER                               	  130688  130815
[   6.2531 ]           60	A_VER                               	  130816  130943
[   6.2531 ] gpt_primary_1_3.bin:
[   6.2531 ] partition_id	partition_name			      StartingLba	EndingLba
[   6.2531 ]            1	APP                                 	 3050048119537623
[   6.2531 ]            2	A_kernel                            	      40  262183
[   6.2531 ]            3	A_kernel-dtb                        	  262184  263719
[   6.2531 ]            4	A_reserved_on_user                  	  263720  328487
[   6.2531 ]            5	B_kernel                            	  328488  590631
[   6.2531 ]            6	B_kernel-dtb                        	  590632  592167
[   6.2532 ]            7	B_reserved_on_user                  	  592168  656935
[   6.2532 ]            8	recovery                            	  656936  820775
[   6.2532 ]            9	recovery-dtb                        	  820776  821799
[   6.2532 ]           10	esp                                 	  821800  952871
[   6.2532 ]           11	recovery_alt                        	  952872 1116711
[   6.2532 ]           12	recovery-dtb_alt                    	 1116712 1117735
[   6.2532 ]           13	esp_alt                             	 1117736 1248807
[   6.2532 ]           14	UDA                                 	 1248832 2068031
[   6.2532 ]           15	reserved                            	 2068032 3050047
[   6.2532 ] gpt_secondary_1_3.bin:
[   6.2532 ] partition_id	partition_name			      StartingLba	EndingLba
[   6.2532 ]            1	APP                                 	 3050048119537623
[   6.2532 ]            2	A_kernel                            	      40  262183
[   6.2532 ]            3	A_kernel-dtb                        	  262184  263719
[   6.2532 ]            4	A_reserved_on_user                  	  263720  328487
[   6.2532 ]            5	B_kernel                            	  328488  590631
[   6.2532 ]            6	B_kernel-dtb                        	  590632  592167
[   6.2532 ]            7	B_reserved_on_user                  	  592168  656935
[   6.2532 ]            8	recovery                            	  656936  820775
[   6.2532 ]            9	recovery-dtb                        	  820776  821799
[   6.2532 ]           10	esp                                 	  821800  952871
[   6.2532 ]           11	recovery_alt                        	  952872 1116711
[   6.2533 ]           12	recovery-dtb_alt                    	 1116712 1117735
[   6.2533 ]           13	esp_alt                             	 1117736 1248807
[   6.2533 ]           14	UDA                                 	 1248832 2068031
[   6.2533 ]           15	reserved                            	 2068032 3050047
[   6.2533 ] 
[   6.3553 ] Get magic id
[   6.3556 ] tegraparser_v2 --get_magic psc_fw
[   6.3558 ] PFWP
[   6.3560 ] partition type psc_fw, magic id = PFWP
[   6.3568 ] tegrahost_v2 --chip 0x23 0 --align pscfw_t234_prod_aligned.bin
[   6.3575 ] tegrahost_v2 --chip 0x23 0 --magicid PFWP --ratchet_blob ratchet_blob.bin --appendsigheader pscfw_t234_prod_aligned.bin zerosbk
[   6.3577 ] Header already present for pscfw_t234_prod_aligned.bin
[   6.3612 ] tegrasign_v3.py --key None --list pscfw_t234_prod_aligned_sigheader.bin_list.xml --pubkeyhash pub_key.key --sha sha512
[   6.3613 ] Assuming zero filled SBK key
[   6.3623 ] Warning: pub_key.key is not found
[   6.3622 ] tegrahost_v2 --chip 0x23 0 --updatesigheader pscfw_t234_prod_aligned_sigheader.bin.encrypt pscfw_t234_prod_aligned_sigheader.bin.hash zerosbk
[   6.3634 ] Get magic id
[   6.3637 ] tegraparser_v2 --get_magic mts_mce
[   6.3638 ] MTSM
[   6.3640 ] partition type mts_mce, magic id = MTSM
[   6.3646 ] tegrahost_v2 --chip 0x23 0 --align mce_flash_o10_cr_prod_aligned.bin
[   6.3652 ] tegrahost_v2 --chip 0x23 0 --magicid MTSM --ratchet_blob ratchet_blob.bin --appendsigheader mce_flash_o10_cr_prod_aligned.bin zerosbk
[   6.3654 ] Header already present for mce_flash_o10_cr_prod_aligned.bin
[   6.3683 ] tegrasign_v3.py --key None --list mce_flash_o10_cr_prod_aligned_sigheader.bin_list.xml --pubkeyhash pub_key.key --sha sha512
[   6.3684 ] Assuming zero filled SBK key
[   6.3694 ] Warning: pub_key.key is not found
[   6.3693 ] tegrahost_v2 --chip 0x23 0 --updatesigheader mce_flash_o10_cr_prod_aligned_sigheader.bin.encrypt mce_flash_o10_cr_prod_aligned_sigheader.bin.hash zerosbk
[   6.3701 ] Get magic id
[   6.3703 ] tegraparser_v2 --get_magic tsec_fw
[   6.3705 ] TSEC
[   6.3706 ] partition type tsec_fw, magic id = TSEC
[   6.3713 ] tegrahost_v2 --chip 0x23 0 --align tsec_t234_aligned.bin
[   6.3719 ] tegrahost_v2 --chip 0x23 0 --magicid TSEC --ratchet_blob ratchet_blob.bin --appendsigheader tsec_t234_aligned.bin zerosbk
[   6.3721 ] Header already present for tsec_t234_aligned.bin
[   6.3751 ] tegrasign_v3.py --key None --list tsec_t234_aligned_sigheader.bin_list.xml --pubkeyhash pub_key.key --sha sha512
[   6.3752 ] Assuming zero filled SBK key
[   6.3763 ] Warning: pub_key.key is not found
[   6.3763 ] tegrahost_v2 --chip 0x23 0 --updatesigheader tsec_t234_aligned_sigheader.bin.encrypt tsec_t234_aligned_sigheader.bin.hash zerosbk
[   6.3772 ] Get magic id
[   6.3774 ] tegraparser_v2 --get_magic mb2_applet
[   6.3776 ] MB2A
[   6.3777 ] partition type mb2_applet, magic id = MB2A
[   6.3782 ] tegrahost_v2 --chip 0x23 0 --align applet_t234_aligned.bin
[   6.3788 ] tegrahost_v2 --chip 0x23 0 --magicid MB2A --ratchet_blob ratchet_blob.bin --appendsigheader applet_t234_aligned.bin zerosbk
[   6.3790 ] adding BCH for applet_t234_aligned.bin
[   6.3844 ] tegrasign_v3.py --key None --list applet_t234_aligned_sigheader.bin_list.xml --pubkeyhash pub_key.key --sha sha512
[   6.3845 ] Assuming zero filled SBK key
[   6.3858 ] Warning: pub_key.key is not found
[   6.3857 ] tegrahost_v2 --chip 0x23 0 --updatesigheader applet_t234_aligned_sigheader.bin.encrypt applet_t234_aligned_sigheader.bin.hash zerosbk
[   6.3871 ] Generating recovery mb2-bct
[   6.3872 ] tegrabct_v2 --chip 0x23 0 --mb2bct mb2_bct.cfg --recov --mb2bctcfg tegra234-mb2-bct-misc-p3701-0000_cpp.dtb --scr tegra234-mb2-bct-scr-p3701-0000_cpp.dtb
[   6.3874 ] ERROR: value 0x31 is out of range
[   6.3882 ] ERROR: value 0x31 is out of range
[   6.3884 ] ERROR: value 0x31 is out of range
[   6.3885 ] ERROR: value 0x31 is out of range
[   6.3887 ] WARNING: unknown property 'tfc_version'
[   6.3888 ] WARNING: unknown property 'addr_header_version'
[   6.3972 ] Updating mb2-bct with storage information for RCM
[   6.3975 ] tegrabct_v2 --chip 0x23 0 --mb2bct mb2_bct_MB2.bct --updatestorageinfo flash.xml.bin
[   6.3996 ] Concatenating mb2-bct to mb2 binary
[   6.3996 ] mb2_bin_file = mb2_t234.bin
[   6.3997 ] mb2_bct_file = mb2_bct_MB2.bct
[   6.4001 ] Get magic id
[   6.4003 ] tegraparser_v2 --get_magic mb2_bootloader
[   6.4005 ] MB2B
[   6.4006 ] partition type mb2_bootloader, magic id = MB2B
[   6.4012 ] tegrahost_v2 --chip 0x23 0 --align mb2_t234_with_mb2_bct_MB2_aligned.bin
[   6.4018 ] tegrahost_v2 --chip 0x23 0 --magicid MB2B --ratchet_blob ratchet_blob.bin --appendsigheader mb2_t234_with_mb2_bct_MB2_aligned.bin zerosbk
[   6.4020 ] adding BCH for mb2_t234_with_mb2_bct_MB2_aligned.bin
[   6.4104 ] tegrasign_v3.py --key None --list mb2_t234_with_mb2_bct_MB2_aligned_sigheader.bin_list.xml --pubkeyhash pub_key.key --sha sha512
[   6.4106 ] Assuming zero filled SBK key
[   6.4122 ] Warning: pub_key.key is not found
[   6.4121 ] tegrahost_v2 --chip 0x23 0 --updatesigheader mb2_t234_with_mb2_bct_MB2_aligned_sigheader.bin.encrypt mb2_t234_with_mb2_bct_MB2_aligned_sigheader.bin.hash zerosbk
[   6.4181 ] Get magic id
[   6.4184 ] tegraparser_v2 --get_magic xusb_fw
[   6.4187 ] XUSB
[   6.4188 ] partition type xusb_fw, magic id = XUSB
[   6.4193 ] tegrahost_v2 --chip 0x23 0 --align xusb_t234_prod_aligned.bin
[   6.4197 ] tegrahost_v2 --chip 0x23 0 --magicid XUSB --ratchet_blob ratchet_blob.bin --appendsigheader xusb_t234_prod_aligned.bin zerosbk
[   6.4198 ] adding BCH for xusb_t234_prod_aligned.bin
[   6.4243 ] tegrasign_v3.py --key None --list xusb_t234_prod_aligned_sigheader.bin_list.xml --pubkeyhash pub_key.key --sha sha512
[   6.4245 ] Assuming zero filled SBK key
[   6.4257 ] Warning: pub_key.key is not found
[   6.4256 ] tegrahost_v2 --chip 0x23 0 --updatesigheader xusb_t234_prod_aligned_sigheader.bin.encrypt xusb_t234_prod_aligned_sigheader.bin.hash zerosbk
[   6.4264 ] Get magic id
[   6.4267 ] tegraparser_v2 --get_magic pva_fw
[   6.4269 ] PVAF
[   6.4269 ] partition type pva_fw, magic id = PVAF
[   6.4284 ] tegrahost_v2 --chip 0x23 0 --align nvpva_020_aligned.fw
[   6.4287 ] tegrahost_v2 --chip 0x23 0 --magicid PVAF --ratchet_blob ratchet_blob.bin --appendsigheader nvpva_020_aligned.fw zerosbk
[   6.4289 ] adding BCH for nvpva_020_aligned.fw
[   6.4622 ] tegrasign_v3.py --key None --list nvpva_020_aligned_sigheader.fw_list.xml --pubkeyhash pub_key.key --sha sha512
[   6.4623 ] Assuming zero filled SBK key
[   6.4651 ] Warning: pub_key.key is not found
[   6.4650 ] tegrahost_v2 --chip 0x23 0 --updatesigheader nvpva_020_aligned_sigheader.fw.encrypt nvpva_020_aligned_sigheader.fw.hash zerosbk
[   6.4686 ] Kernel DTB used: kernel_tegra234-p3737-0000+p3701-0004-nv.dtb
[   6.4686 ] Concatenating kernel-dtb to dce-fw binary
[   6.4687 ] dce_bin = display-t234-dce.bin
[   6.4687 ] kernel_dtb = kernel_tegra234-p3737-0000+p3701-0004-nv.dtb
[   6.4687 ] dce_with_dtb = display-t234-dce_with_kernel_tegra234-p3737-0000+p3701-0004-nv.bin
[   6.6271 ] Get magic id
[   6.6275 ] tegraparser_v2 --get_magic dce_fw
[   6.6277 ] DCEF
[   6.6278 ] partition type dce_fw, magic id = DCEF
[   6.6351 ] tegrahost_v2 --chip 0x23 0 --align display-t234-dce_with_kernel_tegra234-p3737-0000+p3701-0004-nv_aligned.bin
[   6.6356 ] tegrahost_v2 --chip 0x23 0 --magicid DCEF --ratchet_blob ratchet_blob.bin --appendsigheader display-t234-dce_with_kernel_tegra234-p3737-0000+p3701-0004-nv_aligned.bin zerosbk
[   6.6358 ] adding BCH for display-t234-dce_with_kernel_tegra234-p3737-0000+p3701-0004-nv_aligned.bin
[   6.8181 ] tegrasign_v3.py --key None --list display-t234-dce_with_kernel_tegra234-p3737-0000+p3701-0004-nv_aligned_sigheader.bin_list.xml --pubkeyhash pub_key.key --sha sha512
[   6.8183 ] Assuming zero filled SBK key
[   6.8353 ] Warning: pub_key.key is not found
[   6.8353 ] tegrahost_v2 --chip 0x23 0 --updatesigheader display-t234-dce_with_kernel_tegra234-p3737-0000+p3701-0004-nv_aligned_sigheader.bin.encrypt display-t234-dce_with_kernel_tegra234-p3737-0000+p3701-0004-nv_aligned_sigheader.bin.hash zerosbk
[   6.8971 ] Get magic id
[   6.8976 ] tegraparser_v2 --get_magic nvdec
[   6.8977 ] NDEC
[   6.8980 ] partition type nvdec, magic id = NDEC
[   6.8985 ] tegrahost_v2 --chip 0x23 0 --align nvdec_t234_prod_aligned.fw
[   6.8989 ] tegrahost_v2 --chip 0x23 0 --magicid NDEC --ratchet_blob ratchet_blob.bin --appendsigheader nvdec_t234_prod_aligned.fw zerosbk
[   6.8991 ] Header already present for nvdec_t234_prod_aligned.fw
[   6.9027 ] tegrasign_v3.py --key None --list nvdec_t234_prod_aligned_sigheader.fw_list.xml --pubkeyhash pub_key.key --sha sha512
[   6.9028 ] Assuming zero filled SBK key
[   6.9043 ] Warning: pub_key.key is not found
[   6.9042 ] tegrahost_v2 --chip 0x23 0 --updatesigheader nvdec_t234_prod_aligned_sigheader.fw.encrypt nvdec_t234_prod_aligned_sigheader.fw.hash zerosbk
[   6.9055 ] Get magic id
[   6.9058 ] tegraparser_v2 --get_magic bpmp_fw
[   6.9059 ] BPMF
[   6.9061 ] partition type bpmp_fw, magic id = BPMF
[   6.9611 ] tegrahost_v2 --chip 0x23 0 --align bpmp_t234-TE990M-A1_prod_aligned.bin
[   6.9618 ] tegrahost_v2 --chip 0x23 0 --magicid BPMF --ratchet_blob ratchet_blob.bin --appendsigheader bpmp_t234-TE990M-A1_prod_aligned.bin zerosbk
[   6.9621 ] Header already present for bpmp_t234-TE990M-A1_prod_aligned.bin
[   6.9714 ] tegrasign_v3.py --key None --list bpmp_t234-TE990M-A1_prod_aligned_sigheader.bin_list.xml --pubkeyhash pub_key.key --sha sha512
[   6.9716 ] Assuming zero filled SBK key
[   6.9742 ] Warning: pub_key.key is not found
[   6.9743 ] tegrahost_v2 --chip 0x23 0 --updatesigheader bpmp_t234-TE990M-A1_prod_aligned_sigheader.bin.encrypt bpmp_t234-TE990M-A1_prod_aligned_sigheader.bin.hash zerosbk
[   6.9768 ] Using bpmp-dtb concatenated with odmdata
[   6.9768 ] Get magic id
[   6.9770 ] tegraparser_v2 --get_magic bpmp_fw_dtb
[   6.9773 ] BPMD
[   6.9774 ] partition type bpmp_fw_dtb, magic id = BPMD
[   6.9781 ] tegrahost_v2 --chip 0x23 0 --align tegra234-bpmp-3701-0004-3737-0000_with_odm_aligned.dtb
[   6.9786 ] tegrahost_v2 --chip 0x23 0 --magicid BPMD --ratchet_blob ratchet_blob.bin --appendsigheader tegra234-bpmp-3701-0004-3737-0000_with_odm_aligned.dtb zerosbk
[   6.9789 ] adding BCH for tegra234-bpmp-3701-0004-3737-0000_with_odm_aligned.dtb
[   6.9860 ] tegrasign_v3.py --key None --list tegra234-bpmp-3701-0004-3737-0000_with_odm_aligned_sigheader.dtb_list.xml --pubkeyhash pub_key.key --sha sha512
[   6.9862 ] Assuming zero filled SBK key
[   6.9877 ] Warning: pub_key.key is not found
[   6.9876 ] tegrahost_v2 --chip 0x23 0 --updatesigheader tegra234-bpmp-3701-0004-3737-0000_with_odm_aligned_sigheader.dtb.encrypt tegra234-bpmp-3701-0004-3737-0000_with_odm_aligned_sigheader.dtb.hash zerosbk
[   6.9890 ] Get magic id
[   6.9892 ] tegraparser_v2 --get_magic rce_fw
[   6.9895 ] RCEF
[   6.9896 ] partition type rce_fw, magic id = RCEF
[   6.9903 ] tegrahost_v2 --chip 0x23 0 --align camera-rtcpu-t234-rce_aligned.img
[   6.9909 ] tegrahost_v2 --chip 0x23 0 --magicid RCEF --ratchet_blob ratchet_blob.bin --appendsigheader camera-rtcpu-t234-rce_aligned.img zerosbk
[   6.9912 ] adding BCH for camera-rtcpu-t234-rce_aligned.img
[   6.9999 ] tegrasign_v3.py --key None --list camera-rtcpu-t234-rce_aligned_sigheader.img_list.xml --pubkeyhash pub_key.key --sha sha512
[   7.0001 ] Assuming zero filled SBK key
[   7.0014 ] Warning: pub_key.key is not found
[   7.0013 ] tegrahost_v2 --chip 0x23 0 --updatesigheader camera-rtcpu-t234-rce_aligned_sigheader.img.encrypt camera-rtcpu-t234-rce_aligned_sigheader.img.hash zerosbk
[   7.0025 ] Get magic id
[   7.0027 ] tegraparser_v2 --get_magic ape_fw
[   7.0029 ] APEF
[   7.0030 ] partition type ape_fw, magic id = APEF
[   7.0038 ] tegrahost_v2 --chip 0x23 0 --align adsp-fw_aligned.bin
[   7.0044 ] tegrahost_v2 --chip 0x23 0 --magicid APEF --ratchet_blob ratchet_blob.bin --appendsigheader adsp-fw_aligned.bin zerosbk
[   7.0046 ] adding BCH for adsp-fw_aligned.bin
[   7.0126 ] tegrasign_v3.py --key None --list adsp-fw_aligned_sigheader.bin_list.xml --pubkeyhash pub_key.key --sha sha512
[   7.0128 ] Assuming zero filled SBK key
[   7.0142 ] Warning: pub_key.key is not found
[   7.0142 ] tegrahost_v2 --chip 0x23 0 --updatesigheader adsp-fw_aligned_sigheader.bin.encrypt adsp-fw_aligned_sigheader.bin.hash zerosbk
[   7.0155 ] Get magic id
[   7.0158 ] tegraparser_v2 --get_magic spe_fw
[   7.0159 ] SPEF
[   7.0160 ] partition type spe_fw, magic id = SPEF
[   7.0167 ] tegrahost_v2 --chip 0x23 0 --align spe_t234_aligned.bin
[   7.0173 ] tegrahost_v2 --chip 0x23 0 --magicid SPEF --ratchet_blob ratchet_blob.bin --appendsigheader spe_t234_aligned.bin zerosbk
[   7.0175 ] adding BCH for spe_t234_aligned.bin
[   7.0233 ] tegrasign_v3.py --key None --list spe_t234_aligned_sigheader.bin_list.xml --pubkeyhash pub_key.key --sha sha512
[   7.0234 ] Assuming zero filled SBK key
[   7.0248 ] Warning: pub_key.key is not found
[   7.0249 ] tegrahost_v2 --chip 0x23 0 --updatesigheader spe_t234_aligned_sigheader.bin.encrypt spe_t234_aligned_sigheader.bin.hash zerosbk
[   7.0261 ] Get magic id
[   7.0264 ] tegraparser_v2 --get_magic tos
[   7.0266 ] TOSB
[   7.0267 ] partition type tos, magic id = TOSB
[   7.0283 ] tegrahost_v2 --chip 0x23 0 --align tos-optee_t234_aligned.img
[   7.0289 ] tegrahost_v2 --chip 0x23 0 --magicid TOSB --ratchet_blob ratchet_blob.bin --appendsigheader tos-optee_t234_aligned.img zerosbk
[   7.0291 ] adding BCH for tos-optee_t234_aligned.img
[   7.0563 ] tegrasign_v3.py --key None --list tos-optee_t234_aligned_sigheader.img_list.xml --pubkeyhash pub_key.key --sha sha512
[   7.0565 ] Assuming zero filled SBK key
[   7.0599 ] Warning: pub_key.key is not found
[   7.0601 ] tegrahost_v2 --chip 0x23 0 --updatesigheader tos-optee_t234_aligned_sigheader.img.encrypt tos-optee_t234_aligned_sigheader.img.hash zerosbk
[   7.0638 ] Get magic id
[   7.0642 ] tegraparser_v2 --get_magic eks
[   7.0644 ] EKSB
[   7.0646 ] partition type eks, magic id = EKSB
[   7.0650 ] tegrahost_v2 --chip 0x23 0 --align eks_t234_aligned.img
[   7.0657 ] tegrahost_v2 --chip 0x23 0 --magicid EKSB --ratchet_blob ratchet_blob.bin --appendsigheader eks_t234_aligned.img zerosbk
[   7.0659 ] adding BCH for eks_t234_aligned.img
[   7.0668 ] tegrasign_v3.py --key None --list eks_t234_aligned_sigheader.img_list.xml --pubkeyhash pub_key.key --sha sha512
[   7.0670 ] Assuming zero filled SBK key
[   7.0681 ] Warning: pub_key.key is not found
[   7.0680 ] tegrahost_v2 --chip 0x23 0 --updatesigheader eks_t234_aligned_sigheader.img.encrypt eks_t234_aligned_sigheader.img.hash zerosbk
[   7.0717 ] tegrahost_v2 --chip 0x23 0 --align uefi_jetson_with_dtb_aligned.bin
[   7.0722 ] tegrahost_v2 --chip 0x23 0 --magicid CPBL --ratchet_blob ratchet_blob.bin --appendsigheader uefi_jetson_with_dtb_aligned.bin zerosbk
[   7.0724 ] adding BCH for uefi_jetson_with_dtb_aligned.bin
[   7.1287 ] tegrasign_v3.py --key None --list uefi_jetson_with_dtb_aligned_sigheader.bin_list.xml --pubkeyhash pub_key.key --sha sha512
[   7.1288 ] Assuming zero filled SBK key
[   7.1332 ] Warning: pub_key.key is not found
[   7.1331 ] tegrahost_v2 --chip 0x23 0 --updatesigheader uefi_jetson_with_dtb_aligned_sigheader.bin.encrypt uefi_jetson_with_dtb_aligned_sigheader.bin.hash zerosbk
[   7.1382 ] Copying enc\/signed file in /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.1846 ] Copying br bct for multi chains
[   7.1848 ] Signed BCT for boot chain A is copied to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/br_bct_BR.bct

[   7.1848 ] Signed BCT for boot chain B is copied to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/br_bct_b_BR.bct

[   7.1849 ] Copying BCT backup image bct_backup.img to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/bct_backup.img
[   7.1881 ] Copying pscfw_t234_prod_sigheader.bin.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.1885 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/pscfw_t234_prod_sigheader.bin.encrypt
[   7.1885 ] Copying mce_flash_o10_cr_prod_sigheader.bin.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.1887 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/mce_flash_o10_cr_prod_sigheader.bin.encrypt
[   7.1888 ] Copying tsec_t234_sigheader.bin.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.1890 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/tsec_t234_sigheader.bin.encrypt
[   7.1890 ] Copying applet_t234_sigheader.bin.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.1892 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/applet_t234_sigheader.bin.encrypt
[   7.1892 ] Copying mb2_t234_with_mb2_bct_MB2_sigheader.bin.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.1894 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/mb2_t234_with_mb2_bct_MB2_sigheader.bin.encrypt
[   7.1895 ] Copying xusb_t234_prod_sigheader.bin.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.1897 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/xusb_t234_prod_sigheader.bin.encrypt
[   7.1897 ] Copying nvpva_020_sigheader.fw.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.1908 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/nvpva_020_sigheader.fw.encrypt
[   7.1908 ] Copying display-t234-dce_sigheader.bin.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.1959 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/display-t234-dce_sigheader.bin.encrypt
[   7.1959 ] Copying display-t234-dce_with_kernel_tegra234-p3737-0000+p3701-0004-nv_sigheader.bin.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.1998 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/display-t234-dce_with_kernel_tegra234-p3737-0000+p3701-0004-nv_sigheader.bin.encrypt
[   7.1998 ] Copying nvdec_t234_prod_sigheader.fw.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.2000 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/nvdec_t234_prod_sigheader.fw.encrypt
[   7.2001 ] Copying bpmp_t234-TE990M-A1_prod_sigheader.bin.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.2006 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/bpmp_t234-TE990M-A1_prod_sigheader.bin.encrypt
[   7.2006 ] Copying tegra234-bpmp-3701-0004-3737-0000_with_odm_sigheader.dtb.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.2009 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/tegra234-bpmp-3701-0004-3737-0000_with_odm_sigheader.dtb.encrypt
[   7.2009 ] Copying camera-rtcpu-t234-rce_sigheader.img.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.2011 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/camera-rtcpu-t234-rce_sigheader.img.encrypt
[   7.2011 ] Copying adsp-fw_sigheader.bin.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.2014 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/adsp-fw_sigheader.bin.encrypt
[   7.2014 ] Copying spe_t234_sigheader.bin.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.2016 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/spe_t234_sigheader.bin.encrypt
[   7.2016 ] Copying tos-optee_t234_sigheader.img.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.2024 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/tos-optee_t234_sigheader.img.encrypt
[   7.2024 ] Copying eks_t234_sigheader.img.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.2025 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/eks_t234_sigheader.img.encrypt
[   7.2025 ] Copying uefi_jetson_with_dtb_sigheader.bin.encrypt to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed
[   7.2037 ] Signed file: /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/uefi_jetson_with_dtb_sigheader.bin.encrypt
[   7.2053 ] tegraparser_v2 --pt flash.xml.bin --generateflashindex /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader/signed/flash.xml.tmp flash.idx
Using bpmp-dtb concatenated with odmdata in blob for t23x
./tegraflash.py --bl uefi_jetson_with_dtb_sigheader.bin.encrypt --bct br_bct_BR.bct --securedev  --bldtb tegra234-p3737-0000+p3701-0004-nv.dtb --applet rcm_2_encrypt.rcm --applet_softfuse rcm_1_encrypt.rcm --cmd "rcmboot"  --cfg secureflash.xml --chip 0x23 --mb1_bct mb1_bct_MB1_sigheader.bct.encrypt --mem_bct mem_rcm_sigheader.bct.encrypt --mb1_cold_boot_bct mb1_cold_boot_bct_MB1_sigheader.bct.encrypt --mb1_bin mb1_t234_prod_aligned_sigheader.bin.encrypt --psc_bl1_bin psc_bl1_t234_prod_aligned_sigheader.bin.encrypt --mem_bct_cold_boot mem_coldboot_sigheader.bct.encrypt  --bins "psc_fw pscfw_t234_prod_sigheader.bin.encrypt; mts_mce mce_flash_o10_cr_prod_sigheader.bin.encrypt; tsec_fw tsec_t234_sigheader.bin.encrypt; mb2_applet applet_t234_sigheader.bin.encrypt; mb2_bootloader mb2_t234_with_mb2_cold_boot_bct_MB2_sigheader.bin.encrypt; xusb_fw xusb_t234_prod_sigheader.bin.encrypt; pva_fw nvpva_020_sigheader.fw.encrypt; dce_fw display-t234-dce_sigheader.bin.encrypt; nvdec nvdec_t234_prod_sigheader.fw.encrypt; bpmp_fw bpmp_t234-TE990M-A1_prod_sigheader.bin.encrypt; bpmp_fw_dtb tegra234-bpmp-3701-0004-3737-0000_with_odm_sigheader.dtb.encrypt; rce_fw camera-rtcpu-t234-rce_sigheader.img.encrypt; ape_fw adsp-fw_sigheader.bin.encrypt; spe_fw spe_t234_sigheader.bin.encrypt; tos tos-optee_t234_sigheader.img.encrypt; eks eks_t234_sigheader.img.encrypt; kernel boot.img; kernel_dtb tegra234-p3737-0000+p3701-0004-nv.dtb"    --bct_backup 
saving flash command in flashcmd.txt
no_flash ...; prepare rcm blob
Welcome to Tegra Flash
version 1.0.0
Type ? or help for help and q or quit to exit
Use ! to execute system commands
 

 Entering RCM boot

[   0.0116 ] mb1_t234_prod_aligned_sigheader.bin.encrypt filename is from --mb1_bin
[   0.0116 ] psc_bl1_t234_prod_aligned_sigheader.bin.encrypt filename is from --psc_bl1_bin
[   0.0116 ] rcm boot with presigned binaries
[   0.0120 ] Generating blob for T23x
[   0.0127 ] tegrahost_v2 --chip 0x23 0 --generateblob blob.xml blob.bin
[   0.0130 ] The number of images in blob is 19
[   0.0134 ] blobsize is 90071439
[   0.0135 ] Added binary blob_uefi_jetson_with_dtb_sigheader.bin.encrypt of size 3625024
[   0.0412 ] Added binary blob_pscfw_t234_prod_sigheader.bin.encrypt of size 310768
[   0.0416 ] Added binary blob_mce_flash_o10_cr_prod_sigheader.bin.encrypt of size 187120
[   0.0418 ] Added binary blob_tsec_t234_sigheader.bin.encrypt of size 176128
[   0.0419 ] Added binary blob_applet_t234_sigheader.bin.encrypt of size 279616
[   0.0420 ] Not supported type: mb2_applet
[   0.0421 ] Added binary blob_mb2_t234_with_mb2_cold_boot_bct_MB2_sigheader.bin.encrypt of size 439968
[   0.0423 ] Added binary blob_xusb_t234_prod_sigheader.bin.encrypt of size 164864
[   0.0425 ] Added binary blob_nvpva_020_sigheader.fw.encrypt of size 2164640
[   0.0429 ] Added binary blob_display-t234-dce_sigheader.bin.encrypt of size 12110864
[   0.0483 ] Added binary blob_nvdec_t234_prod_sigheader.fw.encrypt of size 294912
[   0.0498 ] Added binary blob_bpmp_t234-TE990M-A1_prod_sigheader.bin.encrypt of size 1027008
[   0.0503 ] Added binary blob_tegra234-bpmp-3701-0004-3737-0000_with_odm_sigheader.dtb.encrypt of size 384768
[   0.0505 ] Added binary blob_camera-rtcpu-t234-rce_sigheader.img.encrypt of size 458096
[   0.0507 ] Added binary blob_adsp-fw_sigheader.bin.encrypt of size 414976
[   0.0508 ] Added binary blob_spe_t234_sigheader.bin.encrypt of size 270336
[   0.0510 ] Added binary blob_tos-optee_t234_sigheader.img.encrypt of size 1633344
[   0.0516 ] Added binary blob_eks_t234_sigheader.img.encrypt of size 9232
[   0.0520 ] Added binary blob_boot.img of size 65828864
[   0.0803 ] Added binary blob_tegra234-p3737-0000+p3701-0004-nv.dtb of size 289807
[   0.1499 ] All RCM required files are saved in rcm_blob folder
done.

*** no-flash flag enabled. Exiting now... *** 

User can run above saved command in factory environment without 
providing pkc and sbk keys to flash a device

Example:

    $ cd bootloader 
    $ sudo bash ./flashcmd.txt

Save initrd flashing command parameters to /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/initrdflashparam.txt
/tmp/tmp.8PxfddBj5m /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra
writing boot image config in bootimg.cfg
extracting kernel in zImage
extracting ramdisk in initrd.img
/tmp/tmp.8PxfddBj5m/initrd /tmp/tmp.8PxfddBj5m /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra
76390 blocks
157022 blocks
/tmp/tmp.8PxfddBj5m /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra
flashimg0=boot0.img
/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra
Success
Cleaning up...
Finish generating flash package.
/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/l4t_initrd_flash_internal.sh --network usb0 --usb-instance 1-5 --device-instance 0 --flash-only --external-device nvme0n1p1 -c "tools/kernel_flash/flash_l4t_external.xml" --network usb0 jetson-agx-orin-devkit nvme0n1p1
# Entry added by NVIDIA initrd flash tool
/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/tmp 127.0.0.1(rw,nohide,insecure,no_subtree_check,async,no_root_squash)
Export list for localhost:
/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/tools/kernel_flash/tmp 127.0.0.1
**********************************************
*                                            *
*  Step 1: Build the flashing environment    *
*                                            *
**********************************************
Create flash environment 0
/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/bootloader /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra
/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra
Finish creating flash environment 0.
****************************************************
*                                                  *
*  Step 2: Boot the device with flash initrd image *
*                                                  *
****************************************************
/home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra/temp_initrdflash/bootloader0 /home/kaka/Desktop/ROS2_software_flashing_tool/flashtool/Linux_for_Tegra
./tegraflash.py --bl uefi_jetson_with_dtb_sigheader.bin.encrypt --bct br_bct_BR.bct --securedev  --bldtb tegra234-p3737-0000+p3701-0004-nv.dtb --applet rcm_2_encrypt.rcm --applet_softfuse rcm_1_encrypt.rcm --cmd "rcmboot"  --cfg secureflash.xml --chip 0x23 --mb1_bct mb1_bct_MB1_sigheader.bct.encrypt --mem_bct mem_rcm_sigheader.bct.encrypt --mb1_cold_boot_bct mb1_cold_boot_bct_MB1_sigheader.bct.encrypt --mb1_bin mb1_t234_prod_aligned_sigheader.bin.encrypt --psc_bl1_bin psc_bl1_t234_prod_aligned_sigheader.bin.encrypt --mem_bct_cold_boot mem_coldboot_sigheader.bct.encrypt  --bins "psc_fw pscfw_t234_prod_sigheader.bin.encrypt; mts_mce mce_flash_o10_cr_prod_sigheader.bin.encrypt; tsec_fw tsec_t234_sigheader.bin.encrypt; mb2_applet applet_t234_sigheader.bin.encrypt; mb2_bootloader mb2_t234_with_mb2_cold_boot_bct_MB2_sigheader.bin.encrypt; xusb_fw xusb_t234_prod_sigheader.bin.encrypt; pva_fw nvpva_020_sigheader.fw.encrypt; dce_fw display-t234-dce_sigheader.bin.encrypt; nvdec nvdec_t234_prod_sigheader.fw.encrypt; bpmp_fw bpmp_t234-TE990M-A1_prod_sigheader.bin.encrypt; bpmp_fw_dtb tegra234-bpmp-3701-0004-3737-0000_with_odm_sigheader.dtb.encrypt; rce_fw camera-rtcpu-t234-rce_sigheader.img.encrypt; ape_fw adsp-fw_sigheader.bin.encrypt; spe_fw spe_t234_sigheader.bin.encrypt; tos tos-optee_t234_sigheader.img.encrypt; eks eks_t234_sigheader.img.encrypt; kernel boot0.img; kernel_dtb tegra234-p3737-0000+p3701-0004-nv.dtb"    --bct_backup  --instance 1-5
Welcome to Tegra Flash
version 1.0.0
Type ? or help for help and q or quit to exit
Use ! to execute system commands
 

 Entering RCM boot

[   0.0219 ] mb1_t234_prod_aligned_sigheader.bin.encrypt filename is from --mb1_bin
[   0.0219 ] psc_bl1_t234_prod_aligned_sigheader.bin.encrypt filename is from --psc_bl1_bin
[   0.0219 ] rcm boot with presigned binaries
[   0.0223 ] tegrarcm_v2 --instance 1-5 --new_session --chip 0x23 0 --uid --download bct_br br_bct_BR.bct --download mb1 mb1_t234_prod_aligned_sigheader.bin.encrypt --download psc_bl1 psc_bl1_t234_prod_aligned_sigheader.bin.encrypt --download bct_mb1 mb1_bct_MB1_sigheader.bct.encrypt
[   0.0225 ] BR_CID: 0x80012344705DF1172C0000000D020080
[   0.0306 ] Sending bct_br
[   0.0372 ] ERROR: might be timeout in USB write.
Error: Return value 3
Command tegrarcm_v2 --instance 1-5 --new_session --chip 0x23 0 --uid --download bct_br br_bct_BR.bct --download mb1 mb1_t234_prod_aligned_sigheader.bin.encrypt --download psc_bl1 psc_bl1_t234_prod_aligned_sigheader.bin.encrypt --download bct_mb1 mb1_bct_MB1_sigheader.bct.encrypt
Cleaning up...
