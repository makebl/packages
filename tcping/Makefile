# SPDX-License-Identifier: GPL-3.0-only
#
# Copyright (C) 2021 ImmortalWrt.org

include $(TOPDIR)/rules.mk

PKG_NAME:=tcping
PKG_RELEASE:=

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/Lienol/tcping.git
PKG_SOURCE_DATE:=2020-07-04
PKG_SOURCE_VERSION:=null
PKG_MIRROR_HASH:=skip

PKG_LICENSE:=GPL-2.0-only
PKG_LICENSE_FILES:=license.txt

PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

define Package/tcping
  SECTION:=net
  CATEGORY:=Network
  TITLE:=tcping measures the latency of a tcp-connection
  URL:=https://github.com/jlyo/tcping
endef

define Package/tcping/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tcping $(1)/usr/bin/
endef

$(eval $(call BuildPackage,tcping))
