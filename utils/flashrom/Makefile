#
# Copyright (C) 2010-2011 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=flashrom
PKG_VERSION:=0.9.7
PKG_RELEASE:=4

PKG_SOURCE:=flashrom-$(PKG_VERSION).tar.bz2
PKG_SOURCE_URL:=http://download.flashrom.org/releases
PKG_MD5SUM:=

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/flashrom
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=Rainmachine FlashROM Utility
  URL:=http://www.flashrom.org/
  DEPENDS:=+zlib  +libftdi +libusb-compat @(mips)
endef

define Package/flashrom/description
 flashrom is a utility for identifying, reading, writing, verifying
 and erasing flash chips. It's often used to flash BIOS/EFI/coreboot
 /firmware images.
endef

MAKE_FLAGS += \
	PREFIX="/usr"

define Package/flashrom/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/flashrom $(1)/usr/sbin/
endef

$(eval $(call BuildPackage,flashrom))
