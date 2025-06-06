# SPDX-License-Identifier: GPL-3.0-or-later
#
# Copyright (C) 2017-2019 Jian Chang <aa65535@live.com>
# Copyright (C) 2021 ImmortalWrt.org

include $(TOPDIR)/rules.mk

PKG_NAME:=simple-obfs
PKG_VERSION:=0.0.5
PKG_RELEASE:=

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/shadowsocks/simple-obfs.git
PKG_SOURCE_DATE:=2019-08-17
PKG_SOURCE_VERSION:=null
PKG_MIRROR_HASH:=skip

PKG_LICENSE:=GPL-3.0-or-later
PKG_LICENSE_FILES:=LICENSE
PKG_MAINTAINER:=Jian Chang <aa65535@live.com>

PKG_BUILD_DEPENDS:=libev
PKG_FIXUP:=autoreconf
PKG_BUILD_PARALLEL:=1
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/simple-obfs/template
  SECTION:=net
  CATEGORY:=Network
  TITLE:=A simple obfuscating tool
  URL:=https://github.com/shadowsocks/simple-obfs
  DEPENDS:=+libpthread +libev
endef

define Package/simple-obfs-client
  $(call Package/simple-obfs/template)
  TITLE+= (client)
  PROVIDES:=simple-obfs
endef

define Package/simple-obfs-server
  $(call Package/simple-obfs/template)
  TITLE+= (server)
endef

define Package/simple-obfs/description
  Simple-obfs is a simple obfusacting tool, designed as plugin server of shadowsocks.
endef

Package/simple-obfs-client/description = $(Package/simple-obfs/description)
Package/simple-obfs-server/description = $(Package/simple-obfs/description)

CONFIGURE_ARGS += \
	--disable-ssp \
	--disable-documentation \
	--disable-assert

define Package/simple-obfs-client/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/obfs-local $(1)/usr/bin/
endef

define Package/simple-obfs-server/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/obfs-server $(1)/usr/bin/
endef

$(eval $(call BuildPackage,simple-obfs-client))
$(eval $(call BuildPackage,simple-obfs-server))
