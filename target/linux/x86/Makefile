#
# Copyright (C) 2006-2011 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk

ARCH:=i386
BOARD:=x86
BOARDNAME:=x86
FEATURES:=squashfs ext4 vdi vmdk pcmcia targz fpu
SUBTARGETS:=generic legacy geode 64
MAINTAINER:=Felix Fietkau <nbd@nbd.name>

KERNEL_PATCHVER:=4.14

KERNELNAME:=bzImage

include $(INCLUDE_DIR)/target.mk

DEFAULT_PACKAGES += partx-utils mkf2fs e2fsprogs \
luci-app-ramfree luci-app-passwall luci-app-pptp-vpnserver-manyusers luci-app-pppoe-server luci-app-pppoe-relay luci-app-v2ray-server luci-app-trojan-server \
luci-app-control-mia luci-app-control-timewol luci-app-control-webrestriction luci-app-control-weburl luci-app-fileassistant\
luci-theme-bootstrap-mc

$(eval $(call BuildTarget))

$(eval $(call $(if $(CONFIG_TARGET_ROOTFS_ISO),RequireCommand,Ignore),mkisofs, \
   	Please install mkisofs. \
))
