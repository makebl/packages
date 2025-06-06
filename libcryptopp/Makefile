#
# Copyright (C) 2021 ImmortalWrt
# <https://immortalwrt.org>
#
# This is free software, licensed under the GNU General Public License v3.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=libcryptopp
PKG_VERSION:=8.5.0
PKG_RELEASE:=

PKG_SOURCE:=cryptopp$(subst .,,$(PKG_VERSION)).zip
PKG_SOURCE_URL:=https://github.com/weidai11/cryptopp/releases/download/CRYPTOPP_$(subst .,_,$(PKG_VERSION))/
PKG_HASH:=skip

PKG_FIXUP:=autoreconf
PKG_BUILD_PARALLEL:=1
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

UNZIP_CMD:=unzip -q -d $(PKG_BUILD_DIR) $(DL_DIR)/$(PKG_SOURCE)

define Package/libcryptopp
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=Free C++ class library of cryptographic schemes
  URL:=https://packages.debian.org/sid/libcrypto++-dev
  DEPENDS:=+libpthread +libstdcpp
endef

define Package/libcryptopp/description
  Crypto++ is library for creating C++ programs which use cryptographic
  algorithms. The library uses a Pipes & Filters architecture with heavy
  use of templates and abstract base classes.
endef

PKG_BUILD_FILE:=cryptopp-autotools$(subst .,,$(PKG_VERSION)).zip
define Download/autotools
  URL:=https://github.com/noloader/cryptopp-autotools/releases/download/CRYPTOPP_$(subst .,_,$(PKG_VERSION))/
  FILE:=$(PKG_BUILD_FILE)
  HASH:=91e06c53b517753f0ba02b92bb259e0ee929ebc6ad4f8b5c190d39ba407d3fbe
endef
$(eval $(call Download,autotools))

define Build/Prepare
	$(PKG_UNPACK)
	unzip -q -d $(PKG_BUILD_DIR) $(DL_DIR)/$(PKG_BUILD_FILE)
	cd $(PKG_BUILD_DIR); rm -f GNUmakefile GNUmakefile-cross
	$(Build/Patch)
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include/cryptopp
	$(CP) $(PKG_INSTALL_DIR)/usr/include/cryptopp/* $(1)/usr/include/cryptopp/
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libcryptopp.{a,so*} $(1)/usr/lib/
endef

define Package/libcryptopp/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libcryptopp.so* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,libcryptopp))
